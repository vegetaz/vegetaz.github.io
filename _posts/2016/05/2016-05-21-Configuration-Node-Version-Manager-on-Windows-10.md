---
layout: post
title: "Cài đặt, cấu hình Node Version Manager trên Windows 10"
date: 2016-05-21 14:25:20 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [nodejs]
---

**Node Version Manager** hay còn gọi là **nvm** cho phép cài đặt, cấu hình và sử dụng độc lập cùng lúc nhiều phiên bản khác nhau của **NodeJS** cùng các gói (package) có liên quan.

`nvm` sử dụng tốt nhất trong môi trường Unix/Linux. Trên Windows cũng có một phiên bản của lập trình viên [Corey Butler](https://github.com/coreybutler). Tải về [vnm-windows](https://github.com/coreybutler/nvm-windows/releases) và tiến hành cài đặt như các phần mềm khác trên Windows.

Kiểm tra số hiệu phiên bản của **nvm**:
```
nvm version
```

Liệt kê danh sách **NodeJS** đã được cài đặt:
```
nvm list
```

Cài đặt một phiên bản có sẵn của **NodeJS**:
```
nvm install 12.14.0
```

Với 12.14.0 là phiên bản có trên máy chủ nodejs.org.  
Đồng thời [npm](https://www.npmjs.com/) cũng được cập nhật.

Để sử dụng phiên bản 12.14.0 của NodeJS thì sử dụng câu lệnh sau:

```
nvm use 12.14.0
```

Có thể chuyển đổi linh hoạt giữa các phiên bản của **NodeJS** bằng lệnh `use` để phù hợp với môi trường phát triển.

**Đọc thêm**:
- [Node Version Manager - POSIX-compliant bash script to manage multiple active node.js versions](https://github.com/nvm-sh/nvm)
- [A node.js version management utility for Windows. Ironically written in Go.](https://github.com/coreybutler/nvm-windows)
- [Node Version Switcher - A cross-platform tool for switching between versions and forks of Node.js](https://github.com/jasongin/nvs)
