---
layout: post
title: "Cài đặt phông chữ Windows TrueType cho Linux Mint"
date: 2013-12-03 07:08:09 +0700
categories: [Information Technology, Software]
tags: [linux]
---

Dùng câu lệnh bên dưới trong cửa sổ `Terminal` để cài đặt phông chữ Windows TrueType cho Linux Mint:  
```console
sudo apt in ttf-mscorefonts-installer
```  

Sau đó, cần chấp nhận các điều khoản của giấy phép Microsoft.  
Để Linux Mint nhận được phông chữ mới, sử dụng câu lệnh sau:  
```console
sudo fc-cache -vr
```  

Để xem danh sách các phông chữ Windows TrueType đã được cài đặt:  
```shell
fc-list
```  

Đọc thêm: [What is ttf-mscorefonts-installer?](https://linuxhint.com/ttf-mscorefonts-installer/)