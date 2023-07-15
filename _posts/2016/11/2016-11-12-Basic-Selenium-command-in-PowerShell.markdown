---
layout: post
title: "Một số câu lệnh cơ bản của Selenium trong PowerShell"
date: 2016-11-12 11:11:11 +0700
categories: [selenium, powershell]
---

### Go to URL
```powershell
$driver.Navigate().GoToURL('https://vegetaz.github.io')
```  

### Get Title
```powershell
$driver.getTitle()
```  

### Get current URL  
```powershell
$driver.getCurrentUrl()
```  

### Get page source
```powershell
$driver.getPageSource()
```  

### Implicit Wait  
Implicit Wait trong Selenium là một cài đặt thời gian chờ mặc định được đặt trên trình điều khiển web cho tất cả các lệnh tìm kiếm phần tử.  
Implicit Wait được sử dụng để tránh các ngoại lệ NoSuchElementException do phần tử không được tải ngay lập tức. Điều này có thể hữu ích khi bạn đang kiểm tra các trang web có nhiều nội dung động, chẳng hạn như trang web có quảng cáo hoặc các phần tử được tải bằng AJAX.  
Tuy nhiên, điều quan trọng cần lưu ý là Implicit Wait có thể làm chậm tốc độ chạy thử nghiệm của bạn. Do đó, bạn nên chỉ sử dụng Implicit Wait khi cần thiết.  
```powershell
$driver.Manage().Timeouts().ImplicitWait = [System.TimeSpan]::FromSeconds($timeoutSeconds)
```  

### Send Keys  
```powershell
$element = $driver.FindElement([OpenQA.Selenium.By]::Id($elementId))
$element.Clear()
$element.SendKeys($value)
```  

### Click  
```powershell
$element = $driver.FindElement([OpenQA.Selenium.By]::ID($elementId))
$element.Click()
```  

### Click by JavaScript  
```powershell
$script = "document.getElementById('$elementId').click();"
$driver.ExecuteScript($script)
```  

### Switch to iframe
```powershell
$driver.SwitchTo().Frame($IframeIdOrName) | Out-Null
```  

### Refresh
```powershell
$driver.Navigate().Refresh()
```  

### Back
```powershell
$driver.Navigate().Back()
```  

### Forward
```powershell
$driver.Navigate().Forward()
```  

### Close web browser  
```powershell
$driver.close()
```  

### Quit web browser  
```powershell
$driver.quit()
```  

### Dispose web browser  
```powershell
$driver.Dispose()
```  

### Find element by Id
```powershell
$driver.FindElement([OpenQA.Selenium.By]::ID($elementId))
```  

### Find element by Xpath
```powershell
$driver.FindElement([OpenQA.Selenium.By]::XPath($elementXpath))
```  

### Find element by Name
```powershell
$driver.FindElement([OpenQA.Selenium.By]::XPath($elementName))
```  

### Find element by Class name
```powershell
$driver.FindElement([OpenQA.Selenium.By]::XPath($elementClassName))
```  

### Find element by Tag name
```powershell
$driver.FindElement([OpenQA.Selenium.By]::XPath($elementTagName))
```  

