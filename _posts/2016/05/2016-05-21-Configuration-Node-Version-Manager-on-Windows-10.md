---
layout: post
title: "Cài đặt, cấu hình Node Version Manager trên Windows 10"
date: 2016-05-21 14:25:20 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [nodejs]
---

Nếu bạn muốn sử dụng NodeJS một cách linh hoạt, hãy sử dụng Node Version Manager hay còn gọi là nvm.  
Phần mềm này cho phép cài đặt, cấu hình và sử dụng độc lập cùng lúc nhiều phiên bản khác nhau của NodeJS cùng các gói có liên quan.

NVM sử dụng tốt nhất trong môi trường Unix/Linux.
Tuy nhiên, trên Windows cũng có một phiên bản của lập trình viên [Corey Butler](https://github.com/coreybutler).

Tải về [nvm-windows](https://vegetaz.github.io/) và tiến hành cài đặt như các phần mềm khác.  
Kiểm tra nvm đã được cài đặt thành công hay chưa với câu lệnh sau trong môi trường Power Shell hoặc Command Prompt

```
nvm version
```

Để kiểm tra các phiên bản NodeJS đã được cài đặt thì sử dụng câu lệnh:

```
nvm list
```

Để cài đặt một phiên bản có sẵn của NodeJS, sử dụng câu lệnh sau:

```
nvm install 12.14.0
```

Với 12.14.0 là phiên bản có trên máy chủ nodejs.org.  
Đồng thời [npm](https://www.npmjs.com/) cũng được cập nhật.

Để sử dụng phiên bản 12.14.0 của NodeJS thì sử dụng câu lệnh sau:

```
nvm use 12.14.0
```

Có thể chuyển đổi linh hoạt giữa các phiên bản của NodeJS bằng lệnh use để phù hợp với môi trường phát triển.

Truy cập vào [Node Version Manager - POSIX-compliant bash script to manage multiple active node.js versions](https://github.com/nvm-sh/nvm) để biết thêm chi tiết.
