---
layout: post
title: "Cài đặt và sử dụng OpenSSH Server trong Linux Mint"
date: 2013-11-09 07:08:09 +0700
categories: [linux, ubuntu, ssh]
---

OpenSSH là một ứng dụng mã nguồn mở được sử dụng để tạo và quản lý các kết nối mạng bảo mật. OpenSSH cung cấp các công cụ để thiết lập kết nối mạng bảo mật và truyền tệp an toàn giữa các máy tính. Nó được sử dụng rộng rãi trong hệ thống Unix và Linux để cung cấp truy cập từ xa an toàn và quản lý hệ thống. OpenSSH bao gồm các thành phần như SSH client và server, các công cụ SSH-keygen, SSH-add và SSH-agent, cho phép người dùng tạo và quản lý các khóa SSH và xác thực bảo mật. Nó được phát triển bởi OpenBSD Project và là một phần của hầu hết các bản phân phối Linux và Unix hiện đại.  

**OpenSSH Client** đã được cài đặt trong hệ thống Linux (Ubuntu, Linux Mint), để kiểm tra có thể sử dụng câu lệnh sau:  
```bash
ssh -V
```  
Các câu lệnh bên dưới áp dụng cho **OpenSSH Server**.  


#### Cập nhật các gói của hệ thống
```bash
sudo apt update
sudo apt upgrade
```  


#### Cài đặt OpenSSH server
```bash
sudo apt install openssh-server
```  


#### Kích hoạt dịch vụ (service) SSH
```bash
sudo systemctl enable ssh
# Hoặc
sudo systemctl enable ssh --now
```  


#### Khởi động service SSH
```bash
sudo systemctl start ssh
```  


#### Kiểm tra trạng thái của service SSH
```bash
sudo systemctl status ssh
```  


#### Tắt tính năng đăng nhập bằng mật khẩu
```bash
sudo nano /etc/ssh/sshd_config
```  
Tìm đến dòng `PasswordAuthentication` và thay đổi thành `no`:  
```bash
PasswordAuthentication no
```  
Tính năng này áp dụng cho trường hợp người dùng muốn đăng nhập bằng key.  


#### Khởi động lại service SSH
```bash
sudo systemctl restart sshd.service
```  


Đọc thêm: [OpenSSH: Manual Pages](https://www.openssh.com/manual.html)
