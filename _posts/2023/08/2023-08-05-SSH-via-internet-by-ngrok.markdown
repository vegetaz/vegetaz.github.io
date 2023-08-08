---
layout: post
title: "SSH qua Internet bằng ngrok"
date: 2023-08-05 14:32:01 +0700
categories: [linux, ubuntu, ssh]
---

**ngrok** là một dịch vụ mã nguồn mở cho phép người dùng truy cập các dịch vụ cục bộ của mình từ internet. Nó hoạt động bằng cách tạo một đường hầm (tunnel) giữa máy tính cục bộ của người dùng và internet, do đó người dùng có thể truy cập các dịch vụ của mình từ bất kỳ đâu. **ngrok** là một công cụ tuyệt vời cho việc phát triển và thử nghiệm các ứng dụng, vì nó cho phép người dùng chia sẻ các ứng dụng của mình với những người khác mà không cần phải thiết lập máy chủ. **ngrok** cũng có thể được sử dụng để tạo các đường hầm bảo mật giữa các máy tính, điều này có thể hữu ích cho việc cộng tác và chia sẻ tệp.

Dưới đây là một số cách sử dụng **ngrok**:
- Phát triển và thử nghiệm các ứng dụng
- Chia sẻ các ứng dụng với những người khác
- Tạo các đường hầm bảo mật giữa các máy tính
- Truy cập các dịch vụ cục bộ từ internet
- Tạo các đường hầm cho các ứng dụng di động
- Tạo các đường hầm cho các máy chủ game
- Tạo các đường hầm cho các thiết bị IoT

**ngrok** là một công cụ mạnh mẽ có thể được sử dụng cho nhiều mục đích khác nhau. Nếu người dùng đang tìm kiếm một cách để truy cập các dịch vụ cục bộ của mình từ internet, thì **ngrok** là một lựa chọn tuyệt vời.

---

Tạo tài khoản **ngrok** trên trang <https://dashboard.ngrok.com/signup>.

Tải về **ngrok** từ <https://ngrok.com/download>

Trên Ubuntu, giải nén **ngrok** vào `/usr/local/bin`:
```bash
 sudo tar xvzf ~/Downloads/ngrok-v3-stable-linux-amd64.tgz -C /usr/local/bin
```

Hoặc cài đặt **ngrok** bằng `apt`:
```bash
curl -s https://ngrok-agent.s3.amazonaws.com/ngrok.asc | sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null && echo "deb https://ngrok-agent.s3.amazonaws.com buster main" | sudo tee /etc/apt/sources.list.d/ngrok.list && sudo apt update && sudo apt install ngrok
```

Đăng nhập vào **ngrok** <https://dashboard.ngrok.com/login> bằng trình duyệt web, đi đến `Getting Started`, sao chép `personal authtoken` trong trang `Your Authtoken`.

Thêm `personal authtoken` vào tệp tin `/home/%username%/.config/ngrok/ngrok.yml`:
```bash
ngrok config add-authtoken <personal-authtoken>
```

Khởi động **ngrok** trên cổng 22:
```bash
ngrok tcp 22
```

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
Từ bây giờ có thể thực hiện điều khiển (remote) `SSH Key` thông qua `ngrok`.

---

**Đọc thêm**:
- [ngrok documentation](https://ngrok.com/docs>)
- [Using ngrok with SSH](https://ngrok.com/docs/using-ngrok-with/ssh/)
