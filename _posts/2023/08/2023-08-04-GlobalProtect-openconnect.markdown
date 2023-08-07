---
layout: post
title: "Cài đặt GlobalProtect-openconnect cho Ubuntu/Linux Mint"
date: 2023-08-04 14:32:01 +0700
categories: [linux, ubuntu]
---

Phần mềm **GlobalProtect VPN** (GUI) dành cho Linux, dựa trên OpenConnect và được xây dựng với Qt5, hỗ trợ chế độ xác thực SAML.
{:refdef: style="text-align: center;"}
![GlobalProtect-openconnect](/static/img/posts/globalprotect/GlobalProtect_Linux_Mint_21.2.png)
{: refdef}


---


#### Thêm ppa:yuezk vào hệ thống
```bash
sudo add-apt-repository ppa:yuezk/globalprotect-openconnect
```


#### Cập nhật hệ thống
```bash
sudo apt update
```


#### Cài đặt GlobalProtect-openconnect
```bash
sudo apt install globalprotect-openconnect
```


Đọc thêm: [**GlobalProtect-openconnect**](https://github.com/yuezk/GlobalProtect-openconnect)
