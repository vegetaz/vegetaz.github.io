---
layout: post
title: "Làm đẹp PowerShell"
date: 2016-06-25 15:25:25 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [powershell]
---

Hôm nay mình sẽ hướng dẫn các bạn làm đẹp cho PowerShell trên Windows 10. Với vài module được cài đặt vào PowerShell, cùng với Windows Terminal được lấy về từ Microsoft Store.

Tất nhiên là không thể thiếu các bộ font phù hợp rồi! :)

Đầu tiên cần sử dụng 2 module, đó là `posh-git` và `oh-my-posh`. Mở PowerShell với quyền Administrator lên và quất 2 câu lệnh dưới đây cho mình:
```bash
Install-Module posh-git -Scope CurrentUser
Install-Module oh-my-posh -Scope CurrentUser
```

Tiếp theo thì quất luôn câu lệnh bên dưới:
```
Install-Module -Name PSReadLine -AllowPrerelease -Scope CurrentUser -Force -SkipPublisherCheck
```

Sau đó chạy tiếp câu lệnh này:
```
notepad $PROFILE
```

Notepad sẽ được khởi động, bạn sao chép và dán 3 dòng dưới đây vào, rồi lưu lại:
```
Import-Module posh-git
Import-Module oh-my-posh
Set-Theme Sorin
```

Ở đây mình sử dụng chủ đề là Sorin, bạn có thể tham khảo các chủ đề có sẵn [tại đây](https://github.com/JanDeDobbeleer/oh-my-posh#themes)!

Tiếp theo là lên [Windows Apps](https://www.microsoft.com/en-us/store/apps/windows) để lấy về [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab), và cấu hình font chữ cho PowerShell là sẽ được một PowerShell đằm thắm hết mức :P

Chúc các bạn thành công!