---
layout: post
title: "Cài đặt Sublime Text cho Linux Mint"
date: 2013-11-07 07:08:09 +0700
categories: [linux]
---

**Sublime Text** là 1 công cụ dùng để  chỉnh sửa mã (code).  

Thêm kho của **Sublime Text** bằng câu lệnh:  
```bash
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/sublimehq-archive.gpg > /dev/null
```  

Chọn kênh (channel) trước khi cài đặt:  
```bash
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```  

Cập nhật danh sách gói hệ thống:  
```bash
sudo apt update
```  

Cài đặt:  
```bash
sudo apt install sublime-text
```  

Nếu có lỗi xảy ra, sử dụng câu lệnh sau trước khi cài đặt:  
```bash
sudo apt install apt-transport-https
```  

Đọc thêm: [Linux Package Manager Repositories](https://www.sublimetext.com/docs/linux_repositories.html)  
