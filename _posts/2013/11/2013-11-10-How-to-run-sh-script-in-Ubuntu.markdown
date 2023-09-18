---
layout: post
title: "Cách thực thi tệp tin .sh trong Ubuntu"
date: 2013-11-09 07:08:09 +0700
categories: [Information Technology, Software, Tech Tips and Tricks]
tags: [linux, ubuntu]
---

**sh** là viết tắt của [shell](https://vegetaz.github.io/posts/shell/). **Shell** là một giao diện dòng lệnh (command-line interface) trong hệ điều hành, cho phép người dùng tương tác với hệ điều hành và thực hiện các lệnh, chương trình hoặc tác vụ khác nhau.

Để thực thi được tệp tin .sh trong môi trường Linux Ubuntu cần phải cấp quyền thực thi cho tệp tin .sh:
```bash
chmod a+x /path/to/yourscript.sh
# Hoặc
sudo chmod a+x /path/to/yourscript.sh
```
Trong đó:
- `a` là all (tất cả), được sử dụng để chỉ định quyền truy cập cho tất cả các người dùng trong hệ thống. 
- `x` là execute (thực thi), đại diện cho quyền được thực thi tệp tin hoặc thư mục tương ứng.

Thực thi tệp tin .sh:
```bash
/path/to/yourscript.sh
# Hoặc
sudo /path/to/yourscript.sh
```

Nếu cửa sổ dòng lệnh (Terminal) mở tại thư mục chứa tệp tin .sh, thì chỉ cần thêm dấu chấm `.` trước tệp tin .sh:
```bash
./yourscript.sh
# Hoặc
sudo ./yourscript.sh
```


**Đọc thêm**: 
- [How do I run .sh scripts?](https://askubuntu.com/questions/38661/how-do-i-run-sh-scripts)
