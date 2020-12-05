---
layout: post
title: "Gỡ bỏ LibreOffice trên Ubuntu"
date: 2016-07-15 15:25:10 +0700
categories: [linux, ubuntu, others]
---

Vì một lý do nào đó mà bạn không thích sử dụng [LibreOffice](https://vi.libreoffice.org/) nữa, bạn có thể thực hiện cách dưới đây để gỡ cài đặt của LibreOffice trên Ubuntu.  

### Gỡ cài đặt
Đầu tiên là câu lệnh gỡ bỏ LibreOffice bằng Terminal:  
```bash
sudo apt-get remove --purge libreoffice*
```

### Làm sạch hệ thống
Tiếp theo là câu lệnh làm sạch, câu lệnh này hơi thừa thãi, không nhất thiết phải thực hiện.  
```bash
sudo apt clean
```

### Gỡ bỏ các thành phần không sử dụng
Cuối cùng là câu lệnh tự động xóa bỏ các thành phần còn sót lại, các thành phần không được sử dụng khi xóa bỏ một gói khỏi hệ thống Ubuntu.   
```bash
sudo apt-get autoremove
```

Tạm biệt LibreOffice, hẹn sớm gặp lại!