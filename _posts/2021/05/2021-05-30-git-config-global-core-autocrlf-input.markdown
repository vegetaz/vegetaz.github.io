---
layout: post
title: "Đảm bảo sự nhất quán về định dạng kết thúc dòng trong Git"
date: 2021-05-30 21:21:21 +0700
categories: [git, linux, windows]
---

Câu lệnh `git config --global core.autocrlf input` được sử dụng để cấu hình Git để xử lý định dạng kết thúc dòng (line ending) trong các tệp tin trong kho lưu trữ (Git Repository).

Chi tiết về từng phần trong câu lệnh:
- `git config` là câu lệnh trong Git để cấu hình các tùy chọn và thiết lập trong Git.  
- `--global` là tùy chọn để áp dụng cấu hình cho toàn bộ hệ thống Git, không chỉ cho một kho lưu trữ cụ thể.  
- `core.autocrlf` là một tùy chọn cấu hình trong Git để điều chỉnh xử lý định dạng kết thúc dòng. Nó có các giá trị sau:  
    + `true` Git tự động chuyển đổi định dạng kết thúc dòng sang CRLF (Windows-style) khi thực hiện commit và chuyển đổi trở lại LF (Unix-style) khi checkout.  
    + `false` Git không thực hiện tự động chuyển đổi định dạng kết thúc dòng. Tệp tin sẽ được lưu trữ và giữ nguyên định dạng ban đầu.  
    + `input` Git tự động chuyển đổi định dạng kết thúc dòng sang LF (Unix-style) khi thực hiện commit và không thực hiện chuyển đổi khi checkout. Đây là tùy chọn thích hợp cho các dự án đa nền tảng hoặc trên Unix/Linux.  

Vậy câu lệnh `git config --global core.autocrlf input` là cấu hình Git để xử lý định dạng kết thúc dòng bằng cách chuyển đổi sang LF (Unix-style) khi commit và giữ nguyên LF khi checkout. Điều này sẽ giúp đảm bảo sự nhất quán về định dạng kết thúc dòng trong kho lưu trữ, đặc biệt khi làm việc trên nhiều nền tảng khác nhau.  

Đọc thêm: [Working with Git on Unix/Linux](https://stackoverflow.com/a/40820527/7106855)
