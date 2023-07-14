---
layout: post
title: "Cài đặt và sử dụng mongosh trên Windows"
date: 2016-07-16 15:25:10 +0700
categories: [others]
---

MongoDB Shell hay còn có tên là `mongosh`.
Để sử dụng được `mongosh` thì máy tính của bạn cần phải cài MongoDB trước đã, hoặc kết nối tới MongoDB Atlas.

`mongosh` vẫn là giao diện dòng lệnh, nhưng trực quan hơn mà không cần sử dụng `pretty()`

### Tải về
Để tải về `mongosh` thì hãy truy cập vào đường dẫn dưới đây:
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
![mongosh](/static/img/posts/mongosh.PNG)
Hoya!