---
layout: post
title: "Cài đặt Ruby cho Linux Mint"
date: 2013-11-01 07:08:09 +0700
categories: [linux]
---

Các câu lệnh dưới đây chạy trong Terminal của Linux Mint.  

Để cài đặt `Ruby` trong `Linux Mint` sử dụng câu lệnh sau:  
```shell
sudo apt-get install ruby-full
```  

Trong trường hợp `apt-get` bị lỗi, sử dụng câu lệnh sau để sửa chữa:  
```shell
sudo apt-get install ruby
```  

Sau khi cài đặt thành công, sử dụng câu lệnh bên dưới để kiểm tra phiên bản của Ruby:  
```shell
ruby -v
```  

Đọc thêm: [Installing Ruby](https://www.ruby-lang.org/en/documentation/installation/#apt)
