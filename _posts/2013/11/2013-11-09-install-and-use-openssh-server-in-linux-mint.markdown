---
layout: post
title: "Cài đặt và sử dụng OpenSSH Server trong Linux Mint"
date: 2013-11-09 07:08:09 +0700
categories: [linux, ubuntu, ssh]
---

**OpenSSH Client** nếu đã được cài đặt trong hệ thống Linux (Ubuntu, Linux Mint), có kiểm tra số hiệu phiên bản bằng câu lệnh sau:  
```bash
ssh -V
```  

---


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


#### Khởi động lại service SSH
```bash
sudo systemctl restart sshd.service
```  


**Đọc thêm**: 
- [SSH](https://vegetaz.github.io/ssh/2013/02/01/ssh.html)
- [OpenSSH: Manual Pages](https://www.openssh.com/manual.html)
