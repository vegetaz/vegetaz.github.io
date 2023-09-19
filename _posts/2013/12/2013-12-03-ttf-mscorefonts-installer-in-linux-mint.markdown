---
layout: post
title: "Cài đặt phông chữ Windows TrueType cho Linux Mint"
date: 2013-12-03 07:08:09 +0700
categories: [Information Technology, Software]
tags: [linux, ubuntu]
---

> Các câu lệnh dưới đây chạy trong **Terminal** của **Linux Mint** hoặc **Ubuntu**.  
{:.prompt-info}

```bash
sudo apt install ttf-mscorefonts-installer
```  

Sau đó, cần chấp nhận các điều khoản của giấy phép Microsoft.  
Để **Linux Mint** hoặc **Ubuntu** nhận được phông chữ mới, sử dụng câu lệnh sau:  
```bash
sudo fc-cache -vr
```  

Để xem danh sách các phông chữ **Windows TrueType** đã được cài đặt:  
```bash
fc-list
```  

**Đọc thêm**:
- [What is ttf-mscorefonts-installer?](https://linuxhint.com/ttf-mscorefonts-installer/)
