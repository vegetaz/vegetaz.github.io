---
layout: post
title: "Kinh nghiệm sử dụng git và github cơ bản của Vận Già"
date: 2013-12-23 00:18:23 +0700
categories: [git]
---

**Cấu hình git cơ bản sau khi cài đặt**

```bash
$ git config --global user.name “Vận Già”
$ git config --global user.email “vegetaz@outlook.com”
```

**Khởi tạo một Repository trong thư mục**

```bash
$ git init
```

**Kết nối Local Repository và Remote Repository**

```bash
$ git remote add origin https://github.com/user-name/repository-name.git
```

**Kiểm tra lại Repository đã được thêm vào**

```bash
$ git remote -v
```

**Đưa tệp tin vào Repository**<br/>
_Đưa tệp tin vào trạng thái tracked_

```bash
$ git add teptin1.file
$ git status
```

**Commit(ghi lại các tệp tin và sự thay đổi với phiên bản trước đó nếu có) tệp tin**

```bash
$ git commit -m "Thêm tệp tin đầu tiên trong cuộc đời"
```

**Đưa tệp tin sau khi Commit lên Remote Repository**

```bash
$ git push -u origin master
```

**Trong trường hợp không thể đưa tệp tin lên Github có thể thử lại:**

```bash
$ git reset --mixed origin/master
$ git add .
$ git commit -m "Nhiều lúc thấy git khó quá!"
$ git push origin master
```

**Hoặc:**

```bash
$ git push -f origin master
```

**Làm việc với Remote Repository**<br/>
_Đồng bộ dữ liệu giữa Remote Repository và Local Repository_

```bash
$ git pull origin master
```

**Sao chép toàn bộ dữ liệu và các thiết lập trên Remote Repository và tự động tạo ra một master branch trên máy tính local.**<br/>
_Lệnh này chỉ nên sử dụng khi bạn cần tạo mới một local repository mới trên máy tính với toàn bộ dữ liệu và thiết lập của remote repository._

```bash
$ git clone remote_repository
```

**Lấy toàn bộ dữ liệu từ Remote Repository nhưng sẽ cho phép gộp thủ công vào một branch nào đó.**

```bash
$ git fetch remote_repository
```

_Vẫn đang cập nhật!_
