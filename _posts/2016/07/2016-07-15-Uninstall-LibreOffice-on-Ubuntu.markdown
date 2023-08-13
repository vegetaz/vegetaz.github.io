---
layout: post
title: "Gỡ bỏ LibreOffice trên Ubuntu"
date: 2016-07-15 15:25:10 +0700
categories: [Information Technology, Software]
tags: [ubuntu]
---

Gỡ bỏ [LibreOffice](https://vi.libreoffice.org/):  
```bash
sudo apt remove --purge libreoffice*
```

Xóa bỏ các gói tin đã được tải về và lưu trữ trong bộ nhớ cache của hệ thống quản lý gói [apt](https://vegetaz.github.io/posts/apt/):
```bash
sudo apt clean
```

Xóa bỏ các gói phần mềm không còn được sử dụng hoặc phụ thuộc không cần thiết trên hệ thống:
```bash
sudo apt autoremove
```

**Đọc thêm**:
- [How to uninstall Libreoffice on Ubuntu in terminal?](https://ask.libreoffice.org/t/how-to-uninstall-libreoffice-on-ubuntu-in-terminal/5179)
- [How to uninstall LibreOffice?](https://askubuntu.com/questions/180403/how-to-uninstall-libreoffice)
