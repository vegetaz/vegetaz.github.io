---
layout: post
title: "Cài đặt GlobalProtect-openconnect cho Ubuntu/Linux Mint"
date: 2023-08-04 14:32:01 +0700
categories: [Information Technology, Software]
tags: [linux, ubuntu]
img_path: /assets/img/GlobalProtect/
---

Phần mềm **GlobalProtect** của Palo Alto Networks là một giải pháp VPN (Virtual Private Network) toàn diện được cung cấp bởi Palo Alto Networks. GlobalProtect được thiết kế để cung cấp một mạng riêng ảo an toàn và bảo mật cho người dùng khi kết nối với mạng công ty từ xa.

Với **GlobalProtect**, người dùng có thể truy cập vào các tài nguyên mạng nội bộ của công ty, như ứng dụng, dữ liệu và hệ thống, một cách an toàn từ bất kỳ đâu trên thế giới, dù đang sử dụng mạng internet công cộng. GlobalProtect sử dụng các công nghệ mã hóa và các lớp bảo mật cao cấp để đảm bảo rằng dữ liệu và thông tin cá nhân của người dùng được bảo vệ khỏi các mối đe dọa mạng.

Ngoài việc cung cấp môi trường truy cập từ xa an toàn, **GlobalProtect** cũng cung cấp các tính năng quản lý mạng linh hoạt, cho phép quản trị viên thiết lập các chính sách bảo mật, theo dõi và kiểm soát việc kết nối từ xa, và cung cấp các báo cáo và nhật ký hoạt động chi tiết.

Tóm lại, **GlobalProtect** là một giải pháp VPN toàn diện của Palo Alto Networks, giúp cung cấp môi trường truy cập từ xa an toàn và quản lý mạng hiệu quả cho các tổ chức và người dùng.

Tải về **GlobalProtect** cho hệ điều hành Linux từ liên kết này: [Cú OneDrive](https://g1915b-my.sharepoint.com/:f:/g/personal/cu2023_g1915b_onmicrosoft_com/EmGh4FAyTjZDt9HS10FchaEBV-3Dv71tkK4cVYhD2lQmkA?e=CQiTQ3)

Giải nén tệp tin `tgz`:
```bash
tar -tvf PanGPLinux-6.1.1-c4.tgz
```
Cài đặt **GlobalProtect**:
```bash
sudo ./gp_install.sh
```

Từ phiên bản Ubuntu 17 trở đi, có thể cần cài đặt thêm gói `resolvconf`:
```bash
sudo apt install resolvconf
```

Trong trường hợp gặp lỗi `SSL Handshake failed` khi xác thực, có thể sửa tệp tin `openssl.cnf`:
```bash
sudo nano /usr/lib/ssl/openssl.cnf
```
Đi đến mục `[system_default_sect]` và thêm đoạn mã này vào:
```shell
Options = UnsafeLegacyRenegotiation
```
Hoặc sử dụng phần mềm `GlobalProtect-openconnect` để thay thế. **GlobalProtect VPN** (GUI) dành cho Linux, dựa trên OpenConnect và được xây dựng với Qt5, hỗ trợ chế độ xác thực `SAML`:
```bash
sudo add-apt-repository ppa:yuezk/globalprotect-openconnect
sudo apt update
sudo apt install globalprotect-openconnect
```
![GlobalProtect-openconnect](GlobalProtect_Linux_Mint_21.2.png)
_GlobalProtect_

Hoặc sử dụng `OpenConnect`, cũng hỗ trợ giao thức VPN của `Palo Alto Network GlobalProtect`:
```bash
sudo apt install openconnect network-manager-openconnect network-manager-openconnect-gnome
```
Trong trường hợp cần cho phép các kết nối `SSH`, `HTTPS` hoạt động liền mạch khi sử dụng `OpenConnect`, có thể cấu hình tường lửa như sau:
```bash
sudo ufw allow OpenSSH
sudo ufw allow http
sudo ufw allow https
sudo ufw enable
sudo ufw status
```


**Đọc thêm**:
- [GlobalProtect-openconnect](https://github.com/yuezk/GlobalProtect-openconnect)
- [OpenConnect](https://www.infradead.org/openconnect/index.html)
