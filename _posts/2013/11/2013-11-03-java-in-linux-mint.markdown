---
layout: post
title: "Cài đặt Java cho Linux Mint"
date: 2013-11-03 07:08:09 +0700
categories: [linux]
---

### Cập nhật
Sử dụng câu lệnh dưới đây trong **Terminal** của **Linux Mint** để cập nhật tất cả các phần mềm trước khi cài đặt Java:  
```bash
sudo apt update && sudo apt upgrade -y
```  

### Cài đặt Java Development Kit
Trước tiên, cần cài đặt **Java Development Kit** (Bộ công cụ phát triển Java - JDK) trên hệ thống bằng dòng lệnh sau:  
```shell
sudo apt install default-jdk
```  

### Cài đặt Java Runtime Environment
Bây giờ, cài đặt **Java Runtime Environment** (JRE) bằng cách thực hiện lệnh sau:
```shell
sudo apt-get install default-jre
```  

### Kiểm tra số hiệu phiên bản của Java
Sau khi cài đặt JDK và JRE hoàn tất, kiểm tra số hiệu phiên bản của Java bằng dòng lệnh sau:  
```shell
java --version
```  

Đọc thêm: [Installation of the JDK on Linux Platforms](https://docs.oracle.com/en/java/javase/20/install/installation-jdk-linux-platforms.html)  
