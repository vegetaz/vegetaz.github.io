---
layout: post
title: "Tạo Windows Form bằng PowerShell"
date: 2013-01-02 07:07:07 +0700
categories: [powershell, windows]
---

### Yêu cầu
[.NET Framework](https://dotnet.microsoft.com/en-us/download/dotnet-framework)  
[PowerShell](https://github.com/PowerShell/PowerShell/releases)  

### Sử dụng
Mở chương trình `Windows PowerShell ISE` hoặc bất kỳ chương trình viết, chỉnh sửa mã (code), khai báo 2 lớp (class) dưới đây:  
```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing
``` 

#### Form
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
