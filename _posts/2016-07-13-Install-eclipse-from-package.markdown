---
layout: post
title: "Tải về và cài đặt eclipse trên Ubuntu"
date: 2016-07-13 15:25:10 +0700
categories: [linux, ubuntu, others]
---

Đây là cách sử dụng Eclipse IDE for Enterprise Java Developers bằng cách download package từ [trang chủ eclipse](https://www.eclipse.org/downloads/packages/).

## Tải về
Truy cập vào trang chủ eclipse, lựa chọn phiên bản phù hợp, ở đây mình lựa chọn Eclipse IDE for Enterprise Java Developers, tiếp theo là gói phù hợp cho hệ điều hành, lựa chọn của mình trong trường hợp này là `Linux x86_64`.  
![Download eclipse](/static/img/install-eclipse/Download_eclipse.png)

### Giải nén
Giải nén tệp tin .tar.gz đã tải về với câu lệnh sau:  
```bash
tar -xvzf eclipse-jee-YYYY-MM-R-linux-gtk-x86_64.tar.gz
```
Sẽ sinh ra 1 thư mục eclipse tại nơi mà bạn đã tải về, có thể chuyển thư mục này tới nơi khác để dễ quản lý.  
Có thể di chuyển thư mục với câu lệnh sau:  
```bash
mv eclipse /opt/
```

### Khởi chạy
Để chạy được chương trình eclipse thì rất dễ, chỉ cần nháy đúp vào biểu tượng eclipse là được.
![eclipse](/static/img/install-eclipse/eclipse.png)
Mỗi lần muốn mở eclipse lên, lại mất nhiều thao tác để tới thư mục của eclipse. Mình là người lười nên tạo luôn đường dẫn khởi chạy cho eclipse:  
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
Bạn có thể kéo biểu tượng eclipse này vào thanh dashboard để tiện dụng hơn.