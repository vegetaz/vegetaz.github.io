---
layout: post
title: "Deploy ứng dụng Java Web lên heroku"
date: 2016-05-22 04:10:03 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [java, web]
---

`heroku` là một dịch vụ máy chủ, đám mây hỗ trợ một số ngôn ngữ lập trình. Trong đó có Java, NodeJS, PHP, ...

Để triển khai ứng dụng Java Web lên `heroku` cần đảm bảo các chương trình sau được cài đặt.

- [git](https://git-scm.com/)
- [heroku](https://www.heroku.com/)
  - `heroku update`
  - `heroku plugins:install heroku-cli-deploy`
  - `heroku login`

Bước thứ nhất là cần tạo một ứng dụng trên trang `heroku`.

Bước thứ hai là commit tất cả các tệp tin có trong thư mục dự án của ứng dụng Java Web.

Bước thứ ba là deploy tệp tin `.war` có trong dự án của ứng dụng Java Web lên `heroku` với câu lệnh `heroku war:deploy target/<war_filename>.war --app <heroku-app-name>`.
![Triển khai ứng dụng Java Web lên heroku](/static/img/posts/deploy-heroku.png)

Sau khi triển khai xong thì mở ứng dụng trên `heroku` với câu lệnh `heroku open --app <heroku-app-name>`.
![Vận Già Blog](/static/img/posts/Lem-heroku.png)

Như vậy là thành công!

**Nguồn**: How to, heroku, Stack Overflow
