---
layout: post
title: "Tạo Windows Form bằng PowerShell"
date: 2013-01-02 07:07:07 +0700
categories: [Information Technology, Software]
tags: [powershell, windows]
---

Windows Forms là một công nghệ giao diện người dùng (GUI) được sử dụng trong các ứng dụng Windows truyền thống. Trong PowerShell, người dùng có thể sử dụng Windows Forms để tạo các ứng dụng giao diện người dùng đơn giản hoặc phức tạp.

Windows Forms không phải là công nghệ giao diện người dùng chính thức của PowerShell. Nếu người dùng muốn phát triển ứng dụng giao diện người dùng phức tạp hơn trong PowerShell, người dùng có thể xem xét sử dụng công nghệ khác như Windows Presentation Foundation (WPF) hoặc Universal Windows Platform (UWP).

### Yêu cầu
[.NET Framework](https://dotnet.microsoft.com/en-us/download/dotnet-framework)  
[PowerShell](https://github.com/PowerShell/PowerShell/releases)  

### Sử dụng
Mở chương trình `Windows PowerShell ISE` hoặc bất kỳ chương trình viết, chỉnh sửa mã (code), khai báo 2 lớp (class) dưới đây:  
```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing
``` 

Khai báo biểu mẫu (form):  
```powershell
$form = New-Object System.Windows.Forms.Form
```  

Tiêu đề (title) cho biểu mẫu:  
```powershell
$form.Text = 'Title là tiêu đề'
```  

Kích thước (size) của biểu mẫu:  
```powershell
$form.Size = New-Object System.Drawing.Size(300,200)
```  

Vị trí (position) của biểu mẫu trên màn hình:  
```powershell
$form.StartPosition = 'CenterScreen'
# Hoặc
$form.StartPosition = [System.Windows.Forms.FormStartPosition]::CenterScreen
```  

Hiển thị biểu mẫu:  
```powershell
$form.ShowDialog()
```  

### Tham khảo
- [Creating a custom input box](https://learn.microsoft.com/en-us/powershell/scripting/samples/creating-a-custom-input-box?view=powershell-5.1)
- [Creating a graphical date picker](https://learn.microsoft.com/en-us/powershell/scripting/samples/creating-a-graphical-date-picker?view=powershell-5.1)
- [Multiple-selection list boxes](https://learn.microsoft.com/en-us/powershell/scripting/samples/multiple-selection-list-boxes?view=powershell-5.1)
- [Selecting items from a list box](https://learn.microsoft.com/en-us/powershell/scripting/samples/selecting-items-from-a-list-box?view=powershell-5.1)
