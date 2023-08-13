---
layout: post
title: "Cài đặt MySQL Server và MySQL Workbench trên Ubuntu"
date: 2016-05-30 05:25:06 +0700
categories: [Information Technology, Software]
tags: [mysql, ubuntu]
---

Để cài đặt được **MySQL Server** và **MySQL Workbench** trên hệ điều hành **Ubuntu Linux** thì cần cập nhật Ubuntu:
```bash
sudo apt update
```

Cài đặt **MySQL Server**
```bash
sudo apt install mysql-server
```

Cấu hình **MySQL Server**
```bash
sudo mysql_secure_installation
```

**MySQL Server** sẽ yêu cầu người dùng thiết lập mật khẩu mạnh mẽ cho tài khoản root, mật khẩu cho tài khoản root phải có ít nhất 1 ký tự viết hoa, 1 ký tự đặc biệt, 1 ký tự số. Và mật khẩu đó nên có 8 ký tự trở lên.

Khởi chạy **MySQL Server**
```bash
sudo mysql
```

Cấu hình cho **MySQL Shell**
```shell
SELECT user,authentication_string,plugin,host FROM mysql.user;
```
```shell
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```
```shell
FLUSH PRIVILEGES;
```

Tải về gói `.deb` của [MySQL Workbench](https://dev.mysql.com/downloads/workbench/), cài đặt và sử dụng.

**Đọc thêm**:
- [MySQL](https://www.mysql.com/)
- [MySQL Community Downloads](https://dev.mysql.com/downloads/mysql/)
- [MySQL Documentation](https://dev.mysql.com/doc/)
