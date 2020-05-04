---
layout: post
title: "Cấu hình, khởi động, tắt server PostgreSQL"
date: 2016-04-26 04:19:22 +0700
categories: [database]
---

Đầu tiên là cần phải [download PostgreSQL](https://www.enterprisedb.com/download-postgresql-binaries) về đã.  
Trong bài viết này mình sử dụng hệ điều hành Windows 10, và sử dụng tệp tin .zip của PostgreSQL để không phải cài đặt.

Tiếp theo là giải nén PostgreSQL ra 1 nơi nào đó trên máy.  
Khai báo PostgreSQL trong `Evironment Variables` của Windows:  
![](/static/img/posts/Variables-2019-12-21.png)

Tạo thêm 1 thư mục `data` để lưu trữ database của PostgreSQL.

Mở Command Prompt với quyền Administrator, và đến thư mục `bin` của PostgreSQL:

```bash
cd D:\Tools\pgsql\bin
```

Sử dụng câu lệnh sau để cấu hình:

```bash
initdb.exe -U postgre -A password -E utf8 -W -D D:\Tools\pgsql\data
```

Trong đó `postgre` là tài khoản đăng nhập, và `password` sẽ được nhập sau khi câu lệnh trên được thực thi.

Như thế này là thành công!
![](/static/img/posts/Success-2019-12-21.png)

Mỗi lần muốn khởi động server của PostgreSQL thì sử dụng câu lệnh:

```bash
pg_ctl -D ^"D^:^\Tools^\pgsql^\data^" -l logfile start
```

Với Command Prompt dưới quyền Administrator.

Có thể sử dụng `pgAdmin4.exe` từ đường dẫn `/pgsql/pgAdmin 4/bin` để sử dụng giao diện quản lý của PostgreSQL.

Để tắt server PostgreSQL thì sử dụng câu lệnh:

```bash
pg_ctl -D ^"D^:^\Tools^\pgsql^\data^" -l logfile stop
```

:)
