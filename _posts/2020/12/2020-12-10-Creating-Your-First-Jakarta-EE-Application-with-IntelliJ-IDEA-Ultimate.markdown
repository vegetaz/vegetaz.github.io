---
layout: post
title: "Tạo dự án Jakarta EE với IntelliJ IDEA"
date: 2020-12-10 16:06:10 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [java, servlet]
img_path: /assets/img/jakarta/
---

**Jakarta** là **Java Platform** được khai sinh ra từ ngày mùng 10 tháng 9 năm 2019 trên nền tảng **Java EE 8**.

### Yêu cầu
- [JDK 8](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html)
- [IDE](https://www.jetbrains.com/idea/download/)
- Java Servlet [Apache Tomcat 9](https://tomcat.apache.org/download-90.cgi).

### Khởi tạo
Từ giao diện chào mừng của IntelliJ IDEA chọn `New Project`
{:refdef: style="text-align: center;"}  
![New Project](NewProject-1.png)
{: refdef}
_New Project_
Tiếp theo là chọn `Java Enterprise` > chọn `Project SDK` là 1.8 phiên bản theo sau tuỳ ý. Tiếp tục với `Project template` là `Web application`, và `Application server` là gì thì tuỳ ý, trong bài viết này là `Tomcat 9.0.37`. Và dĩ nhiên ngôn ngữ để phát triển dự án này là Java rồi, ai thích ngôn khác thì tuỳ ý.
{:refdef: style="text-align: center;"}
![New Project](NewProject-2.png)
{: refdef}
_New Project_
Phần `Specifications` thì chọn là `Servlet`
{:refdef: style="text-align: center;"}
![New Project](NewProject-3.png)
{: refdef}
_New Project_
Và đặt tên, chọn nơi lưu cho dự án vừa khởi tạo
{:refdef: style="text-align: center;"}
![New Project](NewProject-4.png)
{: refdef}
_New Project_

### Chạy chương trình
Giao diện đàu tiên sau khi khởi tạo dự án
{:refdef: style="text-align: center;"}
![Jakarta 2020](Jakarta-1.png)
{: refdef}
_Jakarta 2020_
Chạy thử 
{:refdef: style="text-align: center;"}
![Jakarta 2020](Jakarta-2.png)
{: refdef}
_Jakarta 2020_
Cấu hình 
{:refdef: style="text-align: center;"}
![Jakarta 2020](Jakarta-3.png)
{: refdef}
_Jakarta 2020_

**Đọc thêm**:
- [Jakarta EE](https://jakarta.ee/)
