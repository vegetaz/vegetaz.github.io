---
layout: post
title: "Tải về và cài đặt eclipse trên Ubuntu"
date: 2016-07-13 15:25:10 +0700
categories: [Information Technology, Software]
tags: [linux, ubuntu, others]
img_path: /assets/img/install-eclipse/
---

Đây là cách sử dụng **Eclipse IDE for Enterprise Java Developers** bằng cách tải về gói (package) từ [trang chủ eclipse](https://www.eclipse.org/downloads/packages/).

### Tải về
Truy cập vào trang chủ [eclipse](https://www.eclipse.org/downloads/packages/), lựa chọn phiên bản phù hợp:
{:refdef: style="text-align: center;"}
![Download eclipse](Download_eclipse.png)
{: refdef}
_Download eclipse_

### Cài đặt
Giải nén tệp tin `.tar.gz` đã tải về:  
```bash
tar -xvzf eclipse-jee-YYYY-MM-R-linux-gtk-x86_64.tar.gz
```
```bash
mv eclipse /opt/
```

### Khởi chạy
{:refdef: style="text-align: center;"}
![eclipse](eclipse.png)
{: refdef}
_eclipse_

Tạo đường dẫn khởi chạy cho **eclipse**:  
```bash
sudo gedit /usr/share/applications/eclipse.desktop
```
Sau đó sao chép đoạn mã bên dưới và lưu lại:
```
[Desktop Entry]
Encoding=UTF-8
Name=Eclipse IDE
Type=Application
Exec=/opt/eclipse/eclipse
Icon=/opt/eclipse/icon.xpm
Comment=Integrated Development Environment
```

Đọc thêm:
- [Eclipse documentation](https://help.eclipse.org/latest/index.jsp)
