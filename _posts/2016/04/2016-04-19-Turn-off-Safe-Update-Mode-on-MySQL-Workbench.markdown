---
layout: post
title: "Tắt “Safe Update Mode” trên MySQL Workbench"
date: 2016-04-19 19:39:02 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [mysql]
---

Khi sử dụng MySQL Workbench để thực hiện câu lệnh update, delete dữ liệu sử câu điều kiện WHERE với một column không phải KEY, có trường hợp bạn sẽ gặp 1 lỗi như bên dưới.

```
Error Code: 1175. You are using safe update mode and you tried to update a table without a WHERE that uses a KEY column To disable safe mode, toggle the option in Preferences -> SQL Editor and reconnect.
```

Đây là 1 cơ chế trong MySQL Workbench để cảnh báo cho bạn thực hiện xóa hay update dữ liệu với 1 column không phải là KEY để tránh rủi ro mất mát dữ liệu quá lớn. Tuy nhiên điều này lại gây cho chúng ta phiền hà nhất định. Sau 3.14s tìm kiếm với Google mình đã tìm ra cách tắt “Safe Update Mode” trên MySQL Workbench.

1. Tắt “Safe Update Mode” tạm thời.<br/>
   Bạn có thể tắt tạm thời bằng việc sử dụng câu lệnh: `SET SQL_SAFE_UPDATES = 0;`

Ví dụ khi mình thực hiện update với column my_url không phải là 1 key.

```sql
SET SQL_SAFE_UPDATES = 0;
UPDATE vegetaz_options SET my_url = 'http://vegetaz.github.io' WHERE my_url = 'https://example.com';
SET SQL_SAFE_UPDATES = 1;
```

2. Tắt “Safe Update Mode” vĩnh viễn.<br/>
   Từ **MySQL Workbench** => **Edit** => **Preferences** => **SQL Editor** <br/>
   ![](/static/img/posts/2019-11-19-Disable-Safe-Mode-MySQL-Workbench.png)
   <br/>
   Bỏ tích chọn mục **Safe Updates**

Với các phiên bản cũ các bạn có thể tìm và tắt tùy chọn này ở: **Edit** => **Preferences** => **SQL Queries**.
