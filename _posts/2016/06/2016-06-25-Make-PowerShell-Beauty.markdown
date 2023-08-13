---
layout: post
title: "Làm đẹp PowerShell"
date: 2016-06-25 15:25:25 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [powershell]
---

Làm đẹp cho **PowerShell** trên Windows 10+ với một vài mô-đun (module), cùng với **Windows Terminal** được lấy về từ [Microsoft Store](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab) và các bộ phông chữ phù hợp.

### Cài đặt
```bash
Install-Module posh-git -Scope CurrentUser
```
```powershell
winget install JanDeDobbeleer.OhMyPosh -s winget
```
```
Install-Module -Name PSReadLine -AllowPrerelease -Scope CurrentUser -Force -SkipPublisherCheck
```

### Cấu hình
```
notepad $PROFILE
```
Sao chép và dán 3 dòng dưới đây vào tệp tin `$PROFILE`:
```
Import-Module posh-git
Import-Module oh-my-posh
Set-Theme Sorin
```

**Đọc thêm**:
- [oh-my-posh themes](https://github.com/JanDeDobbeleer/oh-my-posh#themes)
