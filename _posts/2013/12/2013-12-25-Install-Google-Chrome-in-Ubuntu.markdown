---
layout: post
title: "Cài đặt Google Chrome trong Ubuntu"
date: 2013-09-25 11:59:01 +0700
categories: [Information Technology, Software]
tags: [linux, ubuntu]
---

Hướng dẫn cho người mới bắt đầu sử dụng Ubuntu cách cài đặt trình duyệt web Google Chrome. Hướng dẫn này hoạt động trong môi trường dòng lệnh (Terminal) của Ubuntu.

Đầu tiên, cần kiếm tra tình trạng cài đặt của **wget** với câu lệnh kiểm tra phiên bản của wget:
```bash
wget --version
```
Nếu trong cửa sổ dòng lệnh hiển thị như bên dưới thì wget đã được cài đặt:
```
GNU Wget 1.21.2 built on linux-gnu.
```
Trong trường hợp wget chưa cài đặt, sử dụng câu lệnh bên dưới để cài đặt wget:
```bash
sudo apt install wget
```
Sử dụng wget để tải xuống Google Chrome:
```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
```
Cài đặt Google Chrome:
```bash
sudo dpkg -i google-chrome-stable_current_amd64.deb
```
Khởi động Google Chrome:
```bash
google-chrome
```
Gộp các câu lệnh:
```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb | sudo dpkg -i google-chrome-stable_current_amd64.deb | google-chrome | rm google-chrome-stable_current_amd64.deb
```


**Đọc thêm**:
- [Install Google Chrome on Ubuntu](https://itsfoss.com/install-chrome-ubuntu/)
