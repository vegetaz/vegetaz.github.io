---
layout: post
title: "Deploy ứng dụng Java Web lên heroku"
date: 2016-05-22 04:10:03 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [java, web]
img_path: /assets/img/heroku/
---

**heroku** là một nền tảng đám mây (PaaS - Platform as a Service) phổ biến được sử dụng để triển khai và quản lý ứng dụng web. Nó cho phép người dùng dễ dàng triển khai ứng dụng của mình mà không cần quan tâm nhiều đến việc quản lý cơ sở hạ tầng.

### Yêu cầu
- [git](https://git-scm.com/)
- [heroku cli](https://devcenter.heroku.com/articles/heroku-cli)
  + macOS: <https://devcenter.heroku.com/articles/heroku-cli#install-with-an-installer>
  + linux: <https://devcenter.heroku.com/articles/heroku-cli#standalone-installation-with-a-tarball>
  + windows: <https://devcenter.heroku.com/articles/heroku-cli#install-with-an-installer>
- Có tài khoản trên trang [heroku](https://www.heroku.com/)
- Đã tạo một ứng dụng với tên bất kỳ trên trang [heroku](https://www.heroku.com/)

### Cập nhật
```bash
heroku update
```

### Cài đặt plugin
```bash
heroku plugins:install heroku-cli-deploy
```

### Đăng nhập
```bash
heroku login
```

### Deploy
Để deploy tệp tin `.war` có trong dự án của ứng dụng Java Web lên `heroku` sử dụng câu lệnh:
```bash
heroku war:deploy target/<war_filename>.war --app <heroku-app-name>
```
![Triển khai ứng dụng Java Web lên heroku]({{ page.img_path }}deploy-heroku.png)
_Triển khai ứng dụng Java Web lên heroku_

Sau khi triển khai xong thì mở ứng dụng trên `heroku` với câu lệnh:
```bash
heroku open --app <heroku-app-name>
```
![Vận Già Blog]({{ page.img_path }}Lem-heroku.png)
_Vận Già Blog_

**Đọc thêm**:
- [Documentation - Heroku Dev Center](https://devcenter.heroku.com/categories/reference)
