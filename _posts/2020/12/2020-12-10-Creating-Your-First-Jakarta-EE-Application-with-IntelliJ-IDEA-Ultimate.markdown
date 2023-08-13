---
layout: post
title: "Tạo dự án Jakarta EE với IntelliJ IDEA"
date: 2020-12-10 16:06:10 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [java, servlet]
img_path: /assets/img/jakarta/
---

Jakarta ở đây không phải là thành phố của Indonesia, mà là một Java Platform.  
Được khai sinh ra từ ngày mùng 10 tháng 9 năm 2019 trên nền tảng Java EE 8.

### Yêu cầu

Như các dự án JSP/Servlet khác, Jakarta cũng thế, đòi hỏi:
[JDK 8](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html) trở lên, thôi, 8 cho nó quen thuộc.
Một IDE thần thánh, IntelliJ IDEA thần thánh!
Một Java Servlet, ở bài viết này chọn [Apache Tomcat 9](https://tomcat.apache.org/download-90.cgi).

### Khởi tạo

Từ giao diện chào mừng của IntelliJ IDEA chọn `New Project`  
![New Project](NewProject-1.png)
Tiếp theo là chọn `Java Enterprise` > chọn `Project SDK` là 1.8 phiên bản theo sau tuỳ ý. Tiếp tục với `Project template` là `Web application`, và `Application server` là gì thì tuỳ ý, trong bài viết này là `Tomcat 9.0.37`. Và dĩ nhiên ngôn ngữ để phát triển dự án này là Java rồi, ai thích ngôn khác thì tuỳ ý.
![New Project](NewProject-2.png)
Phần `Specifications` thì chọn là `Servlet`  
![New Project](NewProject-3.png)
Và đặt tên, chọn nơi lưu cho dự án vừa khởi tạo
![New Project](NewProject-4.png)

### Chạy chương trình

Giao diện đàu tiên sau khi khởi tạo dự án  
![Jakarta 2020](Jakarta-1.png)
Chạy thử  
![Jakarta 2020](Jakarta-2.png)
Cấu hình  
![Jakarta 2020](Jakarta-3.png)

Hoya!