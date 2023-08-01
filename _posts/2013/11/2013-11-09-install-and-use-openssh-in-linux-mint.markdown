---
layout: post
title: "Cài đặt và sử dụng OpenSSH trong Linux Mint"
date: 2013-11-09 07:08:09 +0700
categories: [linux, ubuntu, ssh]
---

OpenSSH là một ứng dụng mã nguồn mở được sử dụng để tạo và quản lý các kết nối mạng bảo mật. OpenSSH cung cấp các công cụ để thiết lập kết nối mạng bảo mật và truyền tệp an toàn giữa các máy tính. Nó được sử dụng rộng rãi trong hệ thống Unix và Linux để cung cấp truy cập từ xa an toàn và quản lý hệ thống. OpenSSH bao gồm các thành phần như SSH client và server, các công cụ SSH-keygen, SSH-add và SSH-agent, cho phép người dùng tạo và quản lý các khóa SSH và xác thực bảo mật. Nó được phát triển bởi OpenBSD Project và là một phần của hầu hết các bản phân phối Linux và Unix hiện đại.  

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

Đọc thêm: [OpenSSH: Manual Pages](https://www.openssh.com/manual.html)
