---
layout: post
title: "Điều khiển Ubuntu trên Windows thông qua giao thức SSH"
date: 2023-07-30 11:40:01 +0700
categories: [linux, ubuntu, windows]
---

**SSH** (Secure Shell) là một giao thức mạng được sử dụng để thiết lập kết nối mạng bảo mật và đáng tin cậy giữa hai thiết bị, như máy tính từ xa và máy chủ. Nó cung cấp một cách an toàn để truyền tải dữ liệu qua mạng bằng cách mã hóa thông tin gửi đi và nhận về.

Giao thức SSH cho phép người dùng kết nối và điều khiển từ xa các máy tính hoặc máy chủ từ một máy tính khác thông qua mạng. Nó cung cấp các tính năng như xác thực, quản lý phiên, mã hóa dữ liệu và truyền tải các dữ liệu không tin cậy qua mạng công cộng một cách an toàn.

SSH được sử dụng rộng rãi trong quản lý hệ thống và quản trị mạng để thực hiện các tác vụ từ xa như đăng nhập từ xa, điều khiển từ xa, truyền tải tệp tin và thực hiện các lệnh trên máy tính hoặc máy chủ từ xa.

Điểm mạnh của SSH là khả năng xác thực mạnh mẽ, mã hóa dữ liệu và khả năng chống lại các cuộc tấn công từ xa. Do đó, nó là một công cụ quan trọng trong việc bảo mật các kết nối từ xa và truyền tải dữ liệu một cách an toàn qua mạng. 

Ubuntu được cài đặt trong Subsystem (WSL) của Windows.

Trong Ubuntu, cập nhật hệ thống bằng cách chạy lệnh sau:  
```bash
sudo apt update
sudo apt upgrade
```  

Cài đặt **OpenSSH** bằng lệnh sau:  
```bash
sudo apt install openssh-server
```  
Sau khi cài đặt thành công, dịch vụ (service) SSH sẽ được bắt đầu tự động.  

Tiếp theo, xác định địa chỉ IP của Ubuntu bằng dòng lệnh:  
```bash
ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'
```  
Ghi nhớ địa chỉ IP được hiển thị.  

Trên máy tính Windows, mở **Control Panel**, tìm kiếm **Windows Defender Firewall**, chọn **Allow an app or feature through Windows Defender Firewall**, nhấn **Change settings**, tìm **OpenSSH Server**. Kiểm tra cả hai mạng riêng lẫn mạng công cộng cho OpenSSH Server và nhấn **OK**.  

Trên máy tính Windows, mở **Command Prompt** hoặc **PowerShell** hoặc **Windows Terminal**, kết nối tới Ubuntu bằng dòng lệnh:  
```powershell
ssh username@ubuntu-wsl-ip-address
```  
Thay **username** bằng tên người dùng trong Ubuntu và **ubuntu-wsl-ip-address** bằng địa chỉ IP của Ubuntu.  

Đọc thêm:  
- [Remote Development Tips and Tricks](https://code.visualstudio.com/docs/remote/troubleshooting)  
- [Developing in WSL](https://code.visualstudio.com/docs/remote/wsl)
- [Remote development in WSL](https://code.visualstudio.com/docs/remote/wsl-tutorial)  
