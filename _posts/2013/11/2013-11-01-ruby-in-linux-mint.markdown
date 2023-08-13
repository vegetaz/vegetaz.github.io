---
layout: post
title: "Cài đặt Ruby cho Linux Mint"
date: 2013-11-01 07:08:09 +0700
categories: [Information Technology, Software]
tags: [linux]
---

**Ruby** là một ngôn ngữ lập trình động, bậc cao và đa mô hình. Nó được tạo ra bởi Yukihiro Matsumoto (thường được gọi là Matz) vào những năm 1990 tại Nhật Bản. Ruby được thiết kế với mục tiêu kết hợp tính năng của nhiều ngôn ngữ khác nhau để tạo ra một ngôn ngữ dễ đọc, dễ viết và dễ sử dụng.

Ruby được xem là một ngôn ngữ lập trình "ngọt ngào" (syntactically sugar-coated) vì cú pháp của nó rất gần với ngôn ngữ tự nhiên. Cú pháp đơn giản và tự nhiên của Ruby giúp lập trình viên tập trung vào sáng tạo và hiệu suất. Ruby ưu tiên sự đơn giản và sự dễ đọc, giúp tạo ra mã nguồn dễ bảo trì và mở rộng.

Ruby hỗ trợ nhiều mô hình lập trình, bao gồm lập trình hướng đối tượng (OOP), lập trình hàm (functional programming) và lập trình cấu trúc (procedural programming). Nó cũng có các tính năng như quản lý bộ nhớ tự động (garbage collection) và dynamic typing (kiểu dữ liệu động).

Ruby có một cộng đồng lập trình viên tích cực và hỗ trợ mạnh mẽ. Cộng đồng Ruby cung cấp nhiều thư viện, framework và công cụ phát triển phong phú, giúp lập trình viên xây dựng ứng dụng nhanh chóng và hiệu quả.

Ruby cũng nổi tiếng với framework phát triển ứng dụng web Ruby on Rails (hay Rails). Rails là một framework mạnh mẽ, tuân thủ các nguyên tắc của Convention over Configuration (CoC) và Don't Repeat Yourself (DRY), giúp giảm thời gian và công sức phát triển ứng dụng web.

Tóm lại, Ruby là một ngôn ngữ lập trình linh hoạt, dễ đọc và mạnh mẽ, được sử dụng rộng rãi trong lĩnh vực phát triển phần mềm và phát triển ứng dụng web.

---

Để cài đặt **Ruby** trong **Linux Mint** sử dụng câu lệnh sau:  
```bash
sudo apt-get install ruby-full
```  

Trong trường hợp **apt-get** bị lỗi, sử dụng câu lệnh sau để sửa chữa:  
```bash
sudo apt install ruby
```  

Sử dụng câu lệnh bên dưới để cài đặt [Bundler](https://bundler.io/):  
```shell
sudo apt install ruby-bundler
```  

Cài đặt [GCC](https://gcc.gnu.org/):  
```bash
sudo apt install g++
```  

Cài đặt [Make](https://www.gnu.org/software/make/):  
```bash
sudo apt install make
sudo apt install make-guile
```  

Hoặc để cài đặt [gcc](https://gcc.gnu.org/), [g++](https://gcc.gnu.org/) và [Make](https://www.gnu.org/software/make/) trong 1 câu lệnh:  
```bash
sudo apt install build-essential
```  

Sau khi cài đặt thành công, sử dụng câu lệnh bên dưới để kiểm tra phiên bản của **Ruby**:  
```bash
ruby -v
```  

Kiểm tra số hiệu phiên bản của [Ruby Gems](https://rubygems.org/):  
```bash
gem -v
```  

Câu lệnh sau để kiểm tra phiên bản của [Bundler](https://bundler.io/):  
```bash
bundle -v
```  

Câu lệnh sau để kiểm tra phiên bản của [GCC](https://gcc.gnu.org):  
```bash
gcc -v
```  

Câu lệnh sau để kiểm tra phiên bản của [G++](https://gcc.gnu.org):  
```bash
g++ -v
```  

Câu lệnh sau để kiểm tra phiên bản của [Make](https://www.gnu.org/software/make/):  
```bash
make -v
```  

Đọc thêm: [Installing Ruby](https://www.ruby-lang.org/en/documentation/installation/#apt)
