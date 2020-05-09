---
layout: post
title: "Cài đặt MySQL Server và MySQL Workbench trên Ubuntu"
date: 2016-05-30 05:25:06 +0700
categories: [mysql, ubuntu]
---

Để cài đặt được **MySQL Server** và **MySQL Workbench** trên hệ điều hành **Ubuntu Linux** thì bạn cần cập nhật Ubuntu cũng như các thư viện, phần mềm có liên quan bằng câu lệnh huyền thoại trong Terminal
```bash
sudo apt update
```

Sau đó bạn cài đặt MySQL Server
```bash
sudo apt install mysql-server
```

Tiến hành cấu hình MySQL Server
```bash
sudo mysql_secure_installation
```
MySQL Server sẽ yêu cầu bạn thiết lập mật khẩu mạnh mẽ cho tài khoản root, mình khuyên các bạn nên đặt mật khẩu cho tài khoản root phải có ít nhất 1 ký tự viết hoa, 1 ký tự đặc biệt, 1 ký tự số. Và mật khẩu đó nên có 8 ký tự trở lên.
Việc này sẽ thuận lợi hơn trong việc kết nối MySQL Workbench tới MySQL Server.
Đây là chính sách xác thực mới mà cũng không mới của MySQL trên Ubuntu Linux.

Sau đó là khởi chạy MySQL Server
```bash
sudo mysql
```

Thực hiện lần lượt các câu lệnh sau trong MySQL Shell
```shell
SELECT user,authentication_string,plugin,host FROM mysql.user;
```

```shell
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```

```shell
FLUSH PRIVILEGES;
```

Giờ thì bạn chỉ cần tải về gói `.deb` của [MySQL Workbench](https://dev.mysql.com/downloads/workbench/) rồi cài đặt và sử dụng bình thường.

Nguồn: kinh nghiệm bản thân tự mày mò trên Internet và thí nghiệm trên máy ảo.