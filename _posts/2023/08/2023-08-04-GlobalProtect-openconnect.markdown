---
layout: post
title: "Cài đặt GlobalProtect-openconnect cho Ubuntu/Linux Mint"
date: 2023-08-03 14:32:01 +0700
categories: [linux, ubuntu]
---

Phần mềm **GlobalProtect VPN** (GUI) dành cho Linux, dựa trên OpenConnect và được xây dựng với Qt5, hỗ trợ chế độ xác thực SAML.
{:refdef: style="text-align: center;"}
![GlobalProtect-openconnect](https://user-images.githubusercontent.com/3297602/133869036-5c02b0d9-c2d9-4f87-8c81-e44f68cfd6ac.png)
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
