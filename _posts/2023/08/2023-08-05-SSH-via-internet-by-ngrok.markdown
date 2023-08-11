---
layout: post
title: "SSH qua Internet bằng ngrok"
date: 2023-08-05 14:32:01 +0700
categories: [linux, ubuntu, ssh, windows]
---

Tạo tài khoản [**ngrok**](https://vegetaz.github.io/linux/windows/2014/12/04/ngrok.html) trên trang <https://dashboard.ngrok.com/signup>.

Tải về **ngrok** từ <https://ngrok.com/download>

Trên Ubuntu, có thể cài đặt bằng cách giải nén **ngrok** vào `/usr/local/bin`:
```bash
 sudo tar xvzf ~/Downloads/ngrok-v3-stable-linux-amd64.tgz -C /usr/local/bin
```

Hoặc cài đặt **ngrok** bằng `apt`:
```bash
curl -s https://ngrok-agent.s3.amazonaws.com/ngrok.asc | sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null && echo "deb https://ngrok-agent.s3.amazonaws.com buster main" | sudo tee /etc/apt/sources.list.d/ngrok.list && sudo apt update && sudo apt install ngrok
```

Đăng nhập vào **ngrok** <https://dashboard.ngrok.com/login> bằng trình duyệt web, đi đến `Getting Started`, sao chép `personal authtoken` trong trang `Your Authtoken`.

Thêm `personal authtoken` vào tệp tin `/home/%username%/.config/ngrok/ngrok.yml` bằng dòng lệnh:
```bash
ngrok config add-authtoken <personal-authtoken>
```

Khởi động **ngrok** trên cổng (port) `22`:
```bash
ngrok tcp 22
```

**ngrok** đã được khởi động, trạng thái hoạt động:
{:refdef: style="text-align: center;"}
![](/static/img/posts/ngrok/ngrok.png)
{: refdef}

Bây giờ, có thể sử dụng SSH trên máy tính/điện thoại/thiết bị di động có kết nối internet để điều khiển thông qua câu lệnh:
```bash
ssh username-of-server@ngrok-forwarding-address -p ngrok-forwarding-port
```

---

Để sử dụng `SSH Key` thông qua `ngrok`, mỗi lần khởi động `ngrok` trên máy chủ, hãy thay đổi cổng (port) trong tệp tin `config` của máy khách tương ứng với cổng mà `Forwarding` đang hiển thị. Ví dụ `tcp://0.tcp.eu.ngrok.io:99999` thì thay đổi cổng trong tệp tin `config` là:
```
Host 0.tcp.eu.ngrok
  HostName 0.tcp.eu.ngrok
  User username-of-server
  Port 99999
  IdentityFile C:\\Users\\%username%\\.ssh\\id_rsa
```
Sau đó, thực hiện lệnh `ssh-copy-id` trong `Git Bash` để sao chép mã khóa công khai **id_rsa.pub** vào tệp tin **authorized_keys** của máy chủ:
```bash
ssh-copy-id username-of-server@ngrok-forwarding-address
```
Nhập mật khẩu của `username-of-server` để hoàn tất câu lệnh.  
Từ bây giờ, có thể thực hiện điều khiển (remote) `SSH Key` thông qua `ngrok`.

---

**Đọc thêm**:
- [Using ngrok with SSH](https://ngrok.com/docs/using-ngrok-with/ssh/)
