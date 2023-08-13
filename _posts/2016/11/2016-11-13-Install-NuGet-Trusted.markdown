---
layout: post
title: "Cài đặt NuGet"
date: 2016-11-13 11:11:11 +0700
categories: [Information Technology, Software]
tags: [windows, powershell]
---

NuGet được sử dụng có số hiệu phiên bản là 3(v3). Sử dụng trên nền Microsoft PowerShell.  
Cài đặt NuGet v3:  
```powershell
Register-PackageSource -Name NuGet -Location "https://api.nuget.org/v3/index.json" –ProviderName NuGet -Trusted
```  

Kiểm tra trạng thái cài đặt:  
```powershell
Get-PackageSource
```  

Bên cạnh đó cũng có thể thêm `Trusted` cho `PSGallery` vốn có sẵn trong PowerShell:  
```powershell
Register-PSRepository -Default -InstallationPolicy Trusted
```  
Hoặc  
```powershell
Set-PSRepository -Name PSGallery -InstallationPolicy Trusted
```  
Hoặc  
```powershell
Register-PSRepository -Name PSGallery -SourceLocation https://www.powershellgallery.com/api/v2/ -InstallationPolicy Trusted
```  

```powershell
Get-PSRepository
```  

```powershell
Get-PackageProvider
```  

**Đọc thêm**:
- [Install NuGet client tools](https://learn.microsoft.com/en-us/nuget/install-nuget-client-tools)
