---
layout: post
title: "Cài đặt Ruby cho Linux Mint"
date: 2013-11-01 07:08:09 +0700
categories: [linux]
---

Các câu lệnh dưới đây chạy trong **Terminal** của **Linux Mint**.  

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
