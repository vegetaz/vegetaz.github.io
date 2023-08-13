---
layout: post
title: "Kinh nghiệm sử dụng git và github cơ bản của Vận Già"
date: 2013-12-23 00:18:23 +0700
categories: [Information Technology, Software]
tags: [git]
---

### config
> Cấu hình git cơ bản sau khi cài đặt
{:.prompt-info}
```bash
git config --global user.name "Vận Già"
git config --global user.email "vegetaz@outlook.com"
```

### init
> Khởi tạo một Repository trong thư mục
{:.prompt-info}
```bash
git init
```

### remote
> Kết nối Local Repository và Remote Repository
{:.prompt-info}
```bash
git remote add origin https://github.com/user-name/repository-name.git
```
Kiểm tra lại Repository đã được thêm vào
```bash
git remote -v
```

### add
> Đưa tệp tin vào Repository
{:.prompt-info}
```bash
git add teptin1.file
git status
```

### commit
`commit` là ghi lại các tệp tin và sự thay đổi với phiên bản trước đó (nếu có) của tệp tin
```bash
git commit -m "Thêm tệp tin đầu tiên trong cuộc đời"
```

### push
> Đưa tệp tin sau khi Commit lên Remote Repository
{:.prompt-info}
```bash
git push -u origin master
```
Trong trường hợp không thể đưa tệp tin lên Github có thể thử lại:
```bash
git reset --mixed origin/master
git add .
git commit -m "Reset mixed origin master"
git push origin master
```
Hoặc:
```bash
git push -f origin master
```

### pull
> Đồng bộ dữ liệu giữa Remote Repository và Local Repository
{:.prompt-info}
```bash
git pull origin master
```

### clone
> Sao chép toàn bộ dữ liệu và các thiết lập trên Remote Repository và tự động tạo ra một master branch trên máy tính local. Lệnh này chỉ nên sử dụng khi bạn cần tạo mới một local repository mới trên máy tính với toàn bộ dữ liệu và thiết lập của remote repository.
{:.prompt-info}
```bash
git clone remote_repository
```

### fetch
> Lấy toàn bộ dữ liệu từ Remote Repository nhưng sẽ cho phép gộp thủ công vào một branch nào đó.
{:.prompt-info}
```bash
git fetch remote_repository
```

_Còn nữa!_
