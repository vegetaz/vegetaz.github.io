---
layout: post
title: "Cách kiểm tra phiên bản, số hiệu của .NET trên máy tính Windows"
date: 2013-01-01 07:07:07 +0700
categories: [powershell, windows]
---

Sao chép đoạn mã dưới đây, dán vào Windows PowerShell:

```powershell
Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP' -Recurse | Get-ItemProperty -Name version -EA 0 | Where { $_.PSChildName -Match '^(?!S)\p{L}'} | Select PSChildName, version
```

Sau khi đoạn mã được thực thi, sẽ hiển thị ra các phiên bản và số hiệu của .NET đã được cài đặt!

<p class="last-modified-date" style="text-align: right; font-size: 11px; color: #ADADAD;"></p>
