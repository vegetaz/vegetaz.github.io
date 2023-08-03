---
layout: post
title: "Điều khiển Ubuntu trên Windows thông qua giao thức SSH"
date: 2023-07-30 11:40:01 +0700
categories: [linux, ubuntu, windows, ssh]
---

Để cài đặt **OpenSSH Server** trên Ubuntu có thể tham khảo bài viết sau:  
[Cài đặt và sử dụng OpenSSH Server trong Linux Mint](https://vegetaz.github.io/linux/ubuntu/ssh/2013/11/09/install-and-use-openssh-in-linux-mint.html)  


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


Có thể cần cho OpenSSH vào danh sách trắng (whitelist) của tường lửa với cổng (port) 22.  


Trên máy tính Windows, mở **Command Prompt** hoặc **PowerShell** hoặc **Windows Terminal**, kết nối tới Ubuntu bằng dòng lệnh:  
```powershell
ssh username@ubuntu-ip-address
```  
Thay **username** bằng tên người dùng trong Ubuntu và **ubuntu-ip-address** bằng địa chỉ IP của Ubuntu.  


---


Các câu lệnh dưới đây là cho trường hợp sử dụng SSH với key.  

Trên Windows, tạo key với câu lệnh:
```powershell
ssh-keygen
```  
Người dùng sẽ được hỏi nơi để lưu trữ khoá, nhấn Enter để bỏ qua, và sử dụng nơi lưu trữ mặc định.  

Có 2 cặp khoá, **id_rsa** (privatekey - khoá riêng tư) và **id_rsa.pub** (publickey - khoá công khai). **id_rsa** được lưu trữ trên máy tính cá nhân của người dùng. **id_rsa.pub** sẽ được sử dụng để đăng nhập vào máy chủ từ xa.  

Sao chép nội dung **id_rsa.pub** vào bộ nhớ đệm:  
```powershell
type C:\Users\%username%\.ssh\id_rsa.pub | clip
```  


Kết nối đến máy chủ:  
```powershell
ssh <username>@<server>
```  


Tạo tệp tin **authorized_keys**:  
```powershell
mkdir -p ~/.ssh && touch ~/.ssh/authorized_keys
```


Thêm nội dung của **id_rsa.pub** vào **authorized_keys**:
```powershell
echo paste_content_of_id_rsa.pub_to_here >> ~/.ssh/authorized_keys
```  


Đặt quyền truy cập cho tệp tin **authorized_keys**:
```powershell
sudo chmod 700 ~/.ssh && chmod 600 ~/.ssh/authorized_keys
```  


Đọc thêm:  
- [Remote Development Tips and Tricks](https://code.visualstudio.com/docs/remote/troubleshooting)  
- [Developing in WSL](https://code.visualstudio.com/docs/remote/wsl)
- [Remote development in WSL](https://code.visualstudio.com/docs/remote/wsl-tutorial)  
