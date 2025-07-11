---
layout: post
title: "Kết nối tới máy chủ VNC bằng SSH"
date: 2023-09-14 11:59:01 +0700
categories: [Information Technology, Software, Tech Tips and Tricks]
tags: [linux, ubuntu, windows]
img_path: /assets/img/VNC/
---

Kết nối tới máy chủ VNC bằng SSH mang lại lợi ích về bảo mật, tích hợp, vượt qua tường lửa, linh hoạt và quản lý từ xa. Điều này giúp đảm bảo an toàn và thuận tiện trong việc truy cập và quản lý máy chủ VNC từ xa.

### Chuẩn bị
Máy chủ VNC được sử dụng là Ubuntu 20.04 LTS.  
[Ubuntu đã cài đặt và cấu hình SSH Server.](https://vegetaz.github.io/posts/install-and-use-openssh-server-in-linux-mint/)  
Cài đặt trình quản lý đăng nhập:
```bash
sudo apt install lightdm
```
Sau khi cài đặt xong **lightdm** và khởi động lại hệ thống Ubuntu, đi đến **Settings** > **Sharing**, kích hoạt Sharing. Trong Sharing chọn **Remote Desktop** và cấu hình như bên dưới.

![Remote Desktop]({{ page.img_path }}Remote_Desktop.png)
_Remote Desktop_

![Require a password]({{ page.img_path }}Require_a_password.png)
_Require a password_

Khu vực **Password** của **Authentication** sẽ thay đổi theo mỗi lần hệ thống Ubuntu khởi động lại, cần tái thiết lập lại.

### Kết nối
Trên máy khách (trong trường hợp này là máy tính có hệ điều hành Microsoft Windows), cài đặt một chương trình VNC Viewer, [RealVNC Viewer](https://www.realvnc.com/en/connect/download/viewer/) hoặc [TigerVNC Viewer](https://sourceforge.net/projects/tigervnc/files/stable/).
Mở chương trình Command Prompt hoặc PowerShell, nhập vào:
```powershell
ssh -L 5900:localhost:5900 user@host
```
Trong đó:
- `-L` là thiết lập để chuyển tiếp cổng (port forwarding)
- `user` là tên đăng nhập của máy chủ VNC
- `host` là địa chỉ IP của máy chủ VNC

Sau đó, mở chương trình VNC Viewer bất kỳ, nhập vào `localhost:5900` để điều khiển bằng giao thức VNC thông qua SSH.


**Đọc thêm**:
- [Using a VNC Viewer](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/deployment_guide/s1-vnc-viewer)
- [Connecting to VNC Server Using SSH](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/deployment_guide/s1-using_ssh)
