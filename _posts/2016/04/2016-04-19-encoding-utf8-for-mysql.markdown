---
layout: post
title: "Mã hoá UTF-8 trong MySQL"
date: 2016-04-19 02:28:15 +0700
categories: [mysql, database]
---

**MySQL** hỗ trợ nhiều bộ ký tự Unicode:

- `utf8mb4`: Mã hóa UTF-8 của bộ ký tự Unicode sử dụng một đến bốn byte mỗi ký tự.
- `utf8mb3`: Mã hóa UTF-8 của bộ ký tự Unicode sử dụng một đến ba byte mỗi ký tự. Bộ ký tự này đã bị loại bỏ trong MySQL 8.0 và người dùng nên sử dụng `utf8mb4` thay thế.
- `utf8`: Biệt danh cho `utf8mb3`. Trong MySQL 8.0, bí danh này đã bị loại bỏ; hãy sử dụng `utf8mb4` thay thế. `utf8` dự kiến ​​trong một bản phát hành trong tương lai sẽ trở thành một bí danh cho `utf8mb4`.

> **Lưu ý**: Bộ ký tự `utf8mb3` đã bị loại bỏ. Vui lòng sử dụng `utf8mb4` thay thế. `utf8` hiện là một bí danh cho `utf8mb3`, nhưng hiện đã bị loại bỏ với tư cách như vậy, và `utf8` dự kiến ​​sẽ trở thành một tham chiếu đến `utf8mb4`.

> Để tránh nhầm lẫn về ý nghĩa của `utf8`, hãy cân nhắc chỉ định `utf8mb4` rõ ràng cho các tham chiếu bộ ký tự.

**Đọc thêm**:
- [Unicode Character Sets](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode-sets.html)
- [What is the difference between utf8mb4 and utf8 charsets in MySQL?](https://stackoverflow.com/questions/30074492/what-is-the-difference-between-utf8mb4-and-utf8-charsets-in-mysql)
