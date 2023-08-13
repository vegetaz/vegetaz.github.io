---
layout: post
title: "ssh-copy-id"
date: 2013-02-06 17:36:37 +0700
categories: [Information Technology]
tags: [ssh]
---

**ssh-copy-id** là một công cụ dòng lệnh trong [SSH](https://vegetaz.github.io/ssh/2013/02/01/ssh.html) được sử dụng để sao chép khóa công khai của người dùng lên một máy chủ từ xa, để cho phép đăng nhập vào máy chủ đó mà không cần phải nhập mật khẩu. Nó giúp đơn giản hóa quá trình đăng nhập vào máy chủ từ xa bằng cách tự động đăng ký khóa công khai của người dùng trên máy chủ.

---

Cách sử dụng **ssh-copy-id** như sau:  
Mở terminal trên máy tính của người dùng.
Sử dụng lệnh **ssh-copy-id** và cung cấp tên người dùng và địa chỉ IP của máy chủ từ xa:
```bash
ssh-copy-id username@remote_host
```
Nếu đây là lần đầu tiên người dùng đăng nhập vào máy chủ từ xa này, người dùng sẽ được yêu cầu nhập mật khẩu của tài khoản đó. Sau đó, **ssh-copy-id** sẽ sao chép khóa công khai của người dùng lên máy chủ từ xa và thêm nó vào tệp `~/.ssh/authorized_keys` trên máy chủ.
Bây giờ người dùng có thể đăng nhập vào máy chủ từ xa bằng cách sử dụng lệnh **ssh** và không cần phải nhập mật khẩu:
```bash
ssh username@remote_host
```
Lưu ý rằng để sử dụng **ssh-copy-id**, người dùng cần truy cập được vào máy chủ từ xa bằng cách sử dụng tài khoản và mật khẩu của người dùng trên máy chủ đó.

---

**Đọc thêm**:  
- [SSH Copy ID for Copying SSH Keys to Servers](https://www.ssh.com/academy/ssh/copy-id)
