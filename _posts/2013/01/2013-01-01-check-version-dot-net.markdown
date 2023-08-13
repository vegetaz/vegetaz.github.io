---
layout: post
title: "Cách kiểm tra phiên bản, số hiệu của .NET trên máy tính Windows"
date: 2013-01-01 07:07:07 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [powershell, windows]
---

Sao chép đoạn mã dưới đây, dán vào Windows PowerShell:

```powershell
Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP' -Recurse | Get-ItemProperty -Name version -EA 0 | Where { $_.PSChildName -Match '^(?!S)\p{L}'} | Select PSChildName, version
```

Sau khi đoạn mã được thực thi, sẽ hiển thị ra các phiên bản và số hiệu của .NET đã được cài đặt!
```powershell

PSChildName                      Version
-----------                      -------
v2.0.50727                       2.0.50727.4927
v3.0                             3.0.30729.4926
Windows Communication Foundation 3.0.4506.4926
Windows Presentation Foundation  3.0.6920.4902
v3.5                             3.5.30729.4926
Client                           4.8.04084
Full                             4.8.04084
Client                           4.0.0.0
```
