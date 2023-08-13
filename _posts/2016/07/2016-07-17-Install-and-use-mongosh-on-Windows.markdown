---
layout: post
title: "Cài đặt và sử dụng mongosh trên Windows"
date: 2016-07-16 15:25:10 +0700
categories: [Information Technology, Software]
tags: [windows]
img_path: /assets/img/mongosh/
---

**MongoDB Shell** hay còn có tên khác là `mongosh`.
Để sử dụng được `mongosh` thì máy tính cần phải cài đặt **MongoDB**, hoặc kết nối tới **MongoDB Atlas**.
`mongosh` vẫn là giao diện dòng lệnh, nhưng trực quan hơn mà không cần sử dụng thêm `pretty()`

### Tải về
```
https://www.mongodb.com/try/download/shell
```

### Cài đặt
Giải nén tệp tin đã tải về vào một thư mục nào đó: 
```
D:\Tools\mongoshell
```
Tiếp theo là tạo biến môi trường trong `Environment Variables` của Windows cho `mongosh`.

### Sử dụng
Mở trực tiếp tệp tin `mongosh.exe` hoặc gọi `mongosh` từ `PowerShell` hoặc `Command Prompt`.
Để giao diện dễ nhìn hơn có thể sử dụng [Microsoft Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701).
{:refdef: style="text-align: center;"}
![mongosh](mongosh.PNG)
{: refdef}
_mongosh_

**Đọc thêm**:
- [MongoDB Shell](https://www.mongodb.com/docs/mongodb-shell/)
