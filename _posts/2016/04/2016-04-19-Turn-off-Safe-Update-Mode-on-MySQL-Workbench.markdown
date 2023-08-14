---
layout: post
title: "Tắt “Safe Update Mode” trên MySQL Workbench"
date: 2016-04-19 19:39:02 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [mysql]
img_path: /assets/img/mysql/
---

Khi sử dụng **MySQL Workbench** để thực hiện câu lệnh update, delete dữ liệu sử câu điều kiện WHERE với một column không phải KEY, có thể sẽ gặp một số lỗi như bên dưới.
```
Error Code: 1175. You are using safe update mode and you tried to update a table without a WHERE that uses a KEY column To disable safe mode, toggle the option in Preferences -> SQL Editor and reconnect.
```
Đây là một cơ chế trong **MySQL Workbench** để cảnh báo cho người dùng thực hiện xóa hay update dữ liệu với 1 column không phải là KEY để tránh rủi ro mất mát dữ liệu quá lớn.
Dưới đây là cách tắt **Safe Update Mode** trong **MySQL Workbench**.

### Tắt “Safe Update Mode” tạm thời
Có thể tắt tạm thời bằng việc sử dụng câu lệnh: `SET SQL_SAFE_UPDATES = 0;`
```sql
SET SQL_SAFE_UPDATES = 0;
UPDATE vegetaz_options SET my_url = 'http://vegetaz.github.io' WHERE my_url = 'https://example.com';
SET SQL_SAFE_UPDATES = 1;
```

### Tắt “Safe Update Mode” vĩnh viễn
Từ **MySQL Workbench** => **Edit** => **Preferences** => **SQL Editor**
![Tắt “Safe Update Mode” vĩnh viễn](2019-11-19-Disable-Safe-Mode-MySQL-Workbench.png)
_Tắt “Safe Update Mode” vĩnh viễn_
Bỏ tích chọn mục **Safe Updates**

Với các phiên bản cũ, có thể tìm và tắt tùy chọn này ở: **Edit** => **Preferences** => **SQL Queries**.
