---
layout: post
title: "Một số câu lệnh cơ bản của Selenium trong PowerShell"
date: 2016-11-12 11:11:11 +0700
categories: [Information Technology, Tech Tips and Tricks, Testing]
tags: [selenium, powershell]
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

### Submit  
```powershell
$element = $driver.FindElement([OpenQA.Selenium.By]::ID("submit-btn"))
$element.Submit()
```  

### Click by JavaScript  
```powershell
$script = "document.getElementById('$elementId').click();"
$driver.ExecuteScript($script)
```  

### Click to element Xpath by JavaScript  
```powershell
$script = "document.evaluate('$elementXpath', document, null, XPathResult.FIRST_ORDERED_NODE_TYPE, null).singleNodeValue.click();"
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

### Find element by Class name
```powershell
$driver.FindElement([OpenQA.Selenium.By]::ClassName($elementClassName))
```  

### Find element by Css Selector
```powershell
$driver.FindElement([OpenQA.Selenium.By]::CssSelector($elementCssSelector))
```  

### Find element by Equals
```powershell
$driver.FindElement([OpenQA.Selenium.By]::Equals($elementEquals))
```  

### Find element by Id
```powershell
$driver.FindElement([OpenQA.Selenium.By]::Id($elementId))
```  

### Find element by LinkText
```powershell
$driver.FindElement([OpenQA.Selenium.By]::LinkText($elementLinkText))
```  

### Find element by Name
```powershell
$driver.FindElement([OpenQA.Selenium.By]::Name($elementName))
```  

### Find element by PartialLinkText
```powershell
$driver.FindElement([OpenQA.Selenium.By]::PartialLinkText($elementPartialLinkText))
```  

### Find element by ReferenceEquals
```powershell
$driver.FindElement([OpenQA.Selenium.By]::ReferenceEquals($elementReferenceEquals))
```  

### Find element by Tag Name
```powershell
$driver.FindElement([OpenQA.Selenium.By]::TagName($elementTagName))
```  

### Find element by Xpath
```powershell
$driver.FindElement([OpenQA.Selenium.By]::XPath($elementXpath))
```  

**Đọc thêm**:
- [Selenium in PowerShell](https://www.google.com/search?q=Selenium+in+PowerShell&rlz=1C1PNBB_viVN954VN954&oq=Selenium+in+PowerShell&aqs=chrome..69i57j0i19i22i30l4j69i60l3.244j0j4&sourceid=chrome&ie=UTF-8)
