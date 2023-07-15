---
layout: post
title: "Create the user administrator in MongoDB"
date: 2016-06-22 05:25:10 +0700
categories: [database]
---

Mặc định để sử dụng MongoDB thì không cần tài khoản và mật khẩu.
Nhưng trong một số trường hợp cần thiết thì sao?
Ở đây mình đang nói tới trường hợp sử dụng MongoDB tại môi trường localhost.

Đầu tiên cần sử dụng MongoDB ở môi trường dòng lệnh, tiếp theo là truy cập vào admin database với câu lệnh:
```sql
use admin
```

Sau đó sử dụng tập lệnh bên dưới để tạo tài khoản quản trị:
```sql
db.createUser(
  {
    user: "your_user_admin_name",
    pwd: passwordPrompt(),
    roles: [ { role: "userAdminAnyDatabase", db: "admin" }, "readWriteAnyDatabase" ]
  }
)
```
Bạn có thể tuỳ chỉnh tên tuỳ ý của bạn tại phần `your_user_admin_name`, sau đó Enter để thực thi và MongoDB sẽ hỏi mật khẩu mà bạn thiết lập cho user này.

Sau khi thiết lập thành công thì bạn có thể sử dụng user đó với role của administrator!

**Nguồn**: [docs.mongodb.com](https://docs.mongodb.com/manual/tutorial/enable-authentication/)