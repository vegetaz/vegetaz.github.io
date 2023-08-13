---
layout: post
title: "Cài đặt Visual Studio Code cho Linux Mint"
date: 2013-12-01 07:08:09 +0700
categories: [Information Technology, Software]
tags: [linux, ubuntu]
---

> Các câu lệnh dưới đây chạy trong Terminal của Linux Mint hoặc Ubuntu.  
{:.prompt-info}

### Yêu cầu
```bash
sudo apt-get install wget gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg
sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
rm -f packages.microsoft.gpg
```  

### Cập nhật `apt`
```bash
sudo apt install apt-transport-https
sudo apt update
```  

### Cài đặt
```bash
sudo apt install code # or code-insiders
```  

### Khởi chạy
```bash
code
```  

### Cập nhật Visual Studio Code
```bash
sudo apt-get update
sudo apt-get upgrade code
```  

Đọc thêm: [Visual Studio Code on Linux](https://code.visualstudio.com/docs/setup/linux)  
