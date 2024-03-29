---
layout: post
title: "Điều khiển Ubuntu từ Windows thông qua giao thức SSH"
date: 2023-07-30 11:40:01 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [linux, ubuntu, windows, ssh]
---

Để cài đặt **OpenSSH Server** trên Ubuntu có thể tham khảo bài viết sau:  
[Cài đặt và sử dụng OpenSSH Server trong Linux Mint](https://vegetaz.github.io/posts/install-and-use-openssh-server-in-linux-mint/)

---

Xác định địa chỉ IP của Ubuntu bằng dòng lệnh:  
```bash
ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'
```  
Hoặc:  
```bash
ip a
```  
Ghi nhớ địa chỉ IP được hiển thị.  

Trên máy tính Windows, có thể kiểm tra số hiệu phiên bản của **OpenSSH Client** với dòng lệnh:  
```powershell
ssh -V
```
Nếu có số hiệu phiên bản OpenSSH, có nghĩa là nó đã được cài đặt. Nếu không, có thể cài đặt nó bằng cách truy cập vào Settings > Apps > Optional features > Add a feature > OpenSSH Client.

> Có thể cần cho OpenSSH vào danh sách trắng (whitelist) của tường lửa với cổng (port) 22.  
{:.prompt-info}

Trên máy tính Windows, mở **Command Prompt** hoặc **PowerShell** hoặc **Windows Terminal**, kết nối tới Ubuntu bằng dòng lệnh:  
```bash
ssh username@ubuntu-ip-address
```  
Thay **username** bằng tên người dùng trong Ubuntu và **ubuntu-ip-address** bằng địa chỉ IP của Ubuntu.  

---

Các câu lệnh dưới đây là cho trường hợp sử dụng SSH với key.  

Trên Windows, tạo key với câu lệnh:
```bash
ssh-keygen -t rsa
```  
Người dùng sẽ được hỏi nơi để lưu trữ khoá, nhấn Enter để bỏ qua, và sử dụng nơi lưu trữ mặc định.  

> Có 2 cặp khoá, **id_rsa** (privatekey - khoá riêng tư) và **id_rsa.pub** (publickey - khoá công khai). **id_rsa** được lưu trữ trên máy tính cá nhân của người dùng. **id_rsa.pub** sẽ được sử dụng trên máy chủ từ xa.  

Tiếp theo là sao chép nội dung của tệp tin **id_rsa.pub** vào tệp tin **authorized_keys** của máy chủ Linux (Ubuntu).

Sao chép nội dung của tệp tin **id_rsa.pub** vào bộ nhớ đệm:  
```powershell
type C:\Users\%username%\.ssh\id_rsa.pub | clip
```

Kết nối đến máy chủ:  
```bash
ssh username@ubuntu-ip-address
```  

Tạo tệp tin **authorized_keys**:  
```bash
mkdir -p ~/.ssh && touch ~/.ssh/authorized_keys
```

Thêm nội dung của **id_rsa.pub** vào **authorized_keys** bằng dòng lệnh `echo`:
```bash
echo paste_content_of_id_rsa.pub_to_here >> ~/.ssh/authorized_keys
```

Hoặc sử dụng dòng lệnh `scp` để sao chép nội dung của tệp tin **id_rsa.pub** vào tệp tin **authorized_keys** của máy chủ Linux (Ubuntu):
```bash
scp id_rsa.pub ssh username@ubuntu-ip-address:.ssh/authorized_keys
```
> **SCP** là viết tắt của **Secure Copy**. Đây là một công cụ dòng lệnh cho phép người dùng sao chép các tệp và thư mục giữa các máy tính sử dụng giao thức SSH. **SCP** là một cách an toàn để sao chép các tệp vì nó mã hóa tất cả dữ liệu được truyền qua mạng.

Hoặc sử dụng `Git Bash` trên Windows để sao chép mã khóa công khai **id_rsa.pub** lên máy chủ với câu lệnh `ssh-copy-id`:
```bash
ssh-copy-id username@ubuntu-ip-address
```

Đặt quyền truy cập cho tệp tin **authorized_keys**:
```bash
sudo chmod 700 /home/%username% && chmod 700 ~/.ssh && chmod 600 ~/.ssh/authorized_keys
```  

Cấu hình để truy cập bằng SSH key:
```bash
nano /etc/ssh/sshd_config
```
Cho phép 2 dòng lệnh được chạy:
```bash
PubkeyAuthentication yes
AuthorizedKeysFile .ssh/authorized_key
```
Khởi động lại OpenSSH Server:
```
sudo systemctl restart sshd.service
```

Kiểm tra thử:
```bash
ssh username@ubuntu-ip-address
```
Nếu không yêu cầu nhập mật khẩu là thành công.

---

> Có thể cấu hình cho tệp tin `config` trong máy tính Windows.  
Đi đến thư mục `C:\Users\%username%\.ssh` và chỉnh sửa tệp tin `config` bằng chương trình tạo/chỉnh sửa văn bản/mã bất kỳ, với nội dung như sau:
```
Host name-of-ssh-host-here
    User your-user-name-on-host
    HostName host-fqdn-or-ip-goes-here
    IdentityFile ~/.ssh/id-remote-ssh
```
Trên Windows, dòng `IdentityFile ~/.ssh/id-remote-ssh` có thể sử dụng cú pháp thay thế như bên dưới:
```
IdentityFile C:\\Users\\%username%\\.ssh\\id-remote-ssh
```
Ở trường hợp này tệp tin `id-remote-ssh` chính là `id_rsa`.
{:.prompt-info}

---

**Đọc thêm**:  
- [Remote Development Tips and Tricks](https://code.visualstudio.com/docs/remote/troubleshooting)  
- [Developing in WSL](https://code.visualstudio.com/docs/remote/wsl)
- [Remote development in WSL](https://code.visualstudio.com/docs/remote/wsl-tutorial)  
