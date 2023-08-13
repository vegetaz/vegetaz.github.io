---
layout: post
title: "Cài đặt Microsoft .NET Framework 1.1"
date: 2017-01-10 10:25:10 +0700
categories: [Information Technology, Software]
tags: [windows]
img_path: /assets/img/dotNET/
---

Đây là cách cài đặt thủ công .NET Framework 1.1 trên Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2, và Windows 10.

### Kích hoạt các thành phần trong Windows features
Cần kích hoạt .NET Framework 3.5 (Includes .NET 2.0 and 3.0)
{:refdef: style="text-align: center;"}
![Turn Windows features on or off](Turn-Windows-features-on-or-off.PNG)
{: refdef}
_.NET Framework 3.5 (Includes .NET 2.0 and 3.0)_

### Tạo thư mục DotNet
Tạo thư mục DotNet tại ổ cài đặt Windows `C:\DotNet`.  

### Cài đặt Microsoft .NET Framework 1.1
Tải về gói [Microsoft .NET Framework Redistributable 1.1](https://www.microsoft.com/fr-fr/download/confirmation.aspx?id=26), chọn nơi lưu là `C:\DotNet`.  
Mở **Command Prompt** với quyền **Administrator**, thực hiện lệnh `cd` vào thư mục `C:\DotNet` và thực hiện câu lệnh sau:
```
dotnetfx.exe /c:"msiexec.exe /a netfx.msi TARGETDIR=C:\DotNet"
```
Sẽ nhận được thông báo cài đặt thành công như hình ảnh dưới đây:
{:refdef: style="text-align: center;"}
![Installation of Microsoft .NET Framework (English) is complete](Installation-of-Microsoft-.NET-Framework-(English)-is-complete.PNG)
{: refdef}
_Installation of Microsoft .NET Framework (English) is complete_

### Cài đặt Microsoft .NET Framework 1.1 Service Pack 1
Tải về [Microsoft .NET Framework 1.1 Service Pack 1](https://www.microsoft.com/en-us/download/details.aspx?id=33), sẽ được tệp tin `NDP1.1sp1-KB867460-X86.exe`, sao chép tệp tin vào thư mục `C:\DotNet`, đổi tên của nó thành `dotnetfxsp1.exe`. 
Trong cửa sổ **Command Prompt** chạy với quyền **Administrator**, thực hiện câu lệnh sau:
```
dotnetfxsp1.exe /Xp:C:\DotNet\netfxsp.msp
```
Đợi một lát rồi thực hiện câu lệnh tiếp theo:
```
msiexec.exe /a c:\DotNet\netfx.msi /p c:\DotNet\netfxsp.msp
```
Sau khi thực hiện câu lệnh trên xong thì thực thi tệp tin `netfx.msi` có trong thư mục `DotNet`.  
Có thể kiểm tra các phiên bản .NET đã được cài đặt bằng câu lệnh sau trong **Windows PowerShell** với quyền **Administrator**
```
Get-STDotNetVersion
```

**Đọc thêm**:
- [.NET 1.1](https://mega.nz/file/XQlERB5T#f6lTCLgHs0pxikMjZeFw6g6CbUAGDspja4Kit8VvHMs)