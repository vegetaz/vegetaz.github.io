---
layout: post
title: "Mã hoá UTF-8 cho MySQL"
date: 2016-04-19 02:28:15 +0700
categories: [mysql, database]
---

Thủ thuật này mình tham khảo từ trên internet mà quên mất nguồn, vì mình lưu trong OneNote của mình.<br/>
Tác giả bài viết có nói rằng:<br/>

1. Hệ thống cơ sở dữ liệu có các lỗi tinh vi và kỳ quặc, và bạn có thể tránh được rất nhiều lỗi bằng cách tránh các hệ thống cơ sở dữ liệu.<br/>
2. Còn nếu cần phải có database, thì thôi đừng có dùng MySQL hoặc MariaDB. Dùng PostgreSQL đi.<br/>
3. Nếu vẫn nhất quyết dùng MySQL hoặc MariaDB, thì chớ bao giờ dùng **utf8**. Luôn dùng **utf8mb4** khi muốn encoding UTF-8.<br/>

:)
