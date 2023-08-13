---
layout: post
title: "Cài đặt và sử dụng Linux trong Windows"
date: 2023-07-29 18:45:10 +0700
categories: [Information Technology, Tech Tips and Tricks, Software]
tags: [linux, windows]
---

#### Yêu cầu
- Windows 10 có số hiệu phiên bản là 2004 hoặc cao hơn  
- [Windows Subsystem for Linux](https://www.microsoft.com/store/productid/9P9TQF7MRM4R?ocid=pdpshare)

#### Cài đặt
Sử dụng Windows PowerShell hoặc Microsoft Terminal để chạy câu lệnh sau:  
```powershell
wsl --list --online
```  

Chọn 1 **Distro** để cài đặt, ví dụ:  
```powershell
wsl --install -d Ubuntu
```  

Sau một lúc, **Ubuntu** đã được cài đặt, tiến hành thiết lập **username** và **password**.  

Cập nhật **Ubuntu**:  
```bash
sudo apt update && sudo apt upgrade -y && sudo apt dist-upgrade -y && sudo apt autoremove -y
```  

Cài đặt [Xfce Desktop Environment](https://www.xfce.org/):
```bash
sudo apt install --assume-yes xfce4 xfce4-session xfce4-goodies desktop-base dbus-x11 xscreensaver
```  

Cài đặt [xrdp](https://www.xrdp.org/):  
```bash
sudo apt -y install xrdp
```  

Cấu hình [xrdp](https://www.xrdp.org/):  
```bash
sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak
sudo sed -i 's/3389/3390/g' /etc/xrdp/xrdp.ini
sudo sed -i 's/max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini
sudo sed -i 's/xserverbpp=24/#xserverbpp=24\nxserverbpp=128/g' /etc/xrdp/xrdp.ini
```  

Kích hoạt [dbus](https://dbus.freedesktop.org/):  
```bash
sudo systemctl enable dbus
```  

Tắt hệ thống Linux trong Windows:  
```bash
sudo shutdown -r now
```  

Khởi động lại (Restart) hệ thống Windows. Khởi động hệ thống Linux sau khi Windows khởi động bằng cách tìm kiếm `wsl` trong thực đơn (menu) của Windows hoặc chọn Ubuntu từ menu của Windows Terminal hoặc menu của Windows.  

Khởi động [dbus](https://dbus.freedesktop.org/):  
```bash
sudo /etc/init.d/dbus start
```  

Khởi động [xrdp](https://www.xrdp.org/):  
```bash
sudo /etc/init.d/xrdp start
```  

Kiểm tra trạng thái [xrdp](https://www.xrdp.org/):  
```bash
sudo /etc/init.d/xrdp status
```  

Mở chương trình [Remote Desktop Connection](https://support.microsoft.com/en-us/windows/how-to-use-remote-desktop-5fe128d5-8fb1-7a23-3b8a-41e636865e8c) trên Windows, nhập `localhost:3390` vào ô `Computer` và nhấn `Connect`.  

Trong ô Session thì chọn Xorg.  
Nhập vào **username** và **password** đã thiết lập bên trên, nhấn `OK` để vào môi trường làm việc Xfce của Ubuntu.  

Có thể khởi động môi trường làm việc Xfce bằng câu lệnh:  
```bash
export DISPLAY=:0
startx
```  

**Đọc thêm**:  
- [Install Linux on Windows with WSL](https://learn.microsoft.com/en-us/windows/wsl/install)  
- [Manual installation steps for older versions of WSL](https://learn.microsoft.com/en-us/windows/wsl/install-manual)
