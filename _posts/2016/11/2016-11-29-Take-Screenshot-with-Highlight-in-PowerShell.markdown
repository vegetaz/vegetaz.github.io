---
layout: post
title: "Chụp ảnh màn hình của trang web có khoanh vùng bằng Selenium trong PowerShell"
date: 2016-11-29 11:11:11 +0700
categories: [Information Technology, Testing]
tags: [selenium, powershell]
---

Trong PowerShell có thể sử dụng phương thức (medthod) `GetScreenshot()` để chụp ảnh màn hình của trang web. Có thể khoanh vùng phần tử và chụp ảnh màn hình với sự trợ giúp của JavaScript.  

### Xác định phần tử cần khoanh vùng
```powershell
$element = $driver.FindElement([OpenQA.Selenium.By]::XPath($elementXpath))
```  

### Lưu lại kiểu mẫu (style) gốc của phần tử
```powershell
$originalStyle = $element.GetAttribute("style")
```  

### Tạo kiểu khoanh vùng
Trong ví dụ này thì kiểu khoanh vùng có nét đứt, độ rộng 2 pixel và có màu đỏ:
```powershell
$driver.ExecuteScript("arguments[0].setAttribute('style', arguments[1]);", $element, "border: 2px solid red; border-style: dashed;")
```  

### Thực hiện chụp ảnh màn hình:
```powershell
$screenshot = $driver.GetScreenshot()
$screenshot.SaveAsFile('file_name_with_path.png', [OpenQA.Selenium.ScreenshotImageFormat]::Png)
```  

### Trả lại kiểu mẫu (style) gốc cho phần tử:
```powershell
$driver.ExecuteScript("arguments[0].setAttribute('style', arguments[1]);", $element, $originalStyle)
```

**Đọc thêm**:
- [TakeScreenshot](https://www.selenium.dev/documentation/webdriver/interactions/windows/#takescreenshot)
