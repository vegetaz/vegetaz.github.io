---
layout: post
title: "Cuộn trang tới nội dụng muốn xem bằng Selenium trong PowerShell"
date: 2016-11-30 11:30:00 +0700
categories: [Information Technology, Testing]
tags: [selenium, powershell]
---

Nhiều khi muốn chụp ảnh màn hình trang web có thành phần (element) ẩn bên dưới do trang web có nội dung dài hơn chiều cao của màn hình máy tính, lúc chưa biết tới cuộn trang (scroll) thì tôi hay sử dụng Click().  

Nay tôi đã biết có phương thức `scrollIntoView` của JavaScript như bên dưới.  

Thành phần (element) của trang web muốn hiển thị:  
```powershell
$element = $driver.FindElement([OpenQA.Selenium.By]::XPath($elementXpath))
```  

Cuộn (scroll) tới thành phần:  
```powershell
$driver.executeScript("arguments[0].scrollIntoView(true);", $element)
```  

**Đọc thêm**:
- [Scroll to element](https://www.selenium.dev/documentation/webdriver/actions_api/wheel/#scroll-to-element)
