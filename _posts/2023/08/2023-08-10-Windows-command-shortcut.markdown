---
layout: post
title: "Các câu lệnh rút ngắn trong Windows"
date: 2023-08-10 14:32:01 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [windows]
---

Các câu lệnh rút ngắn (command shortcut) trong Windows giúp ích rất nhiều cho người dùng trong việc truy cập nhanh vào các tuỳ chọn, tác vụ, vân vân trong Windows.

Các lệnh rút ngắn này có thể sử dụng bằng phím tắt `⊞ + R` hoặc trong môi trường dòng lệnh (Command Prompt, PowerShell).

### Computer Management
```cmd
compmgmt.msc
```

### Network Connections
```cmd
ncpa.cpl
```

### Local Users and Groups
```cmd
lusrmgr.msc
```

### Disk Cleanup
```cmd
cleanmgr
```

### Region
```cmd
intl.cpl
```
### Active User
```cmd
net user Administrator /active:yes
```

### Add a User to a Local Group
```cmd
net localgroup Administrators vegetaz@outlook.com /add
```

### Add an AzureAD User to a Local Group
```cmd
net localgroup Administrators AzureAD\vegetaz@onmicrosoft.com /add
```

**Xem thêm**:
- [Windows keyboard shortcuts](https://support.microsoft.com/en-us/windows/windows-keyboard-shortcuts-3d444b08-3a00-abd6-67da-ecfc07e86b98)
- [Windows Keyboard shortcuts](https://ss64.com/nt/syntax-keyboard.html)
