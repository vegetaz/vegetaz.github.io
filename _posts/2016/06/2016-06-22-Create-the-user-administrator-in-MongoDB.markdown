---
layout: post
title: "Create the user administrator in MongoDB"
date: 2016-06-22 05:25:10 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [database]
---

Mặc định để sử dụng MongoDB thì không cần tài khoản và mật khẩu.

Chạy câu lệnh bên dưới để sử dụng tài khoản `admin`:
```sql
use admin
```

Tạo thêm tài khoản có quyền quản trị:
```sql
db.createUser(
  {
    user: "your_user_admin_name",
    pwd: passwordPrompt(),
    roles: [ { role: "userAdminAnyDatabase", db: "admin" }, "readWriteAnyDatabase" ]
  }
)
```

**Đọc thêm**: 
- [docs.mongodb.com](https://docs.mongodb.com/manual/tutorial/enable-authentication/)
