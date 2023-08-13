---
layout: post
title: "Chạy Selenium trong môi trường Windows PowerShell"
date: 2016-11-11 11:11:11 +0700
categories: [Information Technology, Tech Tips and Tricks, Testing]
tags: [selenium, powershell]
---

# Tải về
Tải về 2 gói `.nupkg` là `Selenium.WebDriver` và `Selenium.Support` từ trang nuget.org lần lượt bên dưới:
```
https://www.nuget.org/packages/Selenium.WebDriver
https://www.nuget.org/packages/Selenium.Support
```
Tiếp theo là `ChromeDriver` và `GeckoDriver` tùy vào bạn sử dụng trình duyệt Chrome hay Firefox.
```
http://chromedriver.storage.googleapis.com/index.html
https://github.com/mozilla/geckodriver/releases/
```
Nhớ chọn tệp tin `.exe` trùng với số hiệu phiên bản của Chrome hoặc Firefox đã được cài đặt.

# Cài đặt
Tạo một thư mục trống, ví dụ là `SeleniumPowerShellTest`:   
```
D:\SeleniumPowerShellTest
```
Sao chép tệp tin `WebDriver.dll` từ thư mục `lib` của gói `.nupkg` sang thư mục đã tạo. Nếu bạn đã cài .NET có số hiệu phiên bản là `4.0` thì sử dụng tệp tin `WebDriver.dll` có trong thư mục `4.0`.  
Sao chép tệp tin `WebDriver.Support.dll` từ thư mục `lib` của gói `.nupkg` sang thư mục đã tạo. Nếu bạn đã cài .NET có số hiệu phiên bản là `4.0` thì sử dụng tệp tin `WebDriver.Support.dll` có trong thư mục `4.0`.  
Di chuyển tệp tin `chromedriver.exe` hoặc `geckodriver.exe` vào thư mục `SeleniumPowerShellTest` tùy vào trường hợp sử dụng trình duyệt Chrome hoặc Firefox.
Tạo một tệp tin PowerShell, ví dụ `TestSPS.ps1`.  
Mở tệp tin `TestSPS.ps1` bằng chương trình Windows PowerShell ISE hoặc Notepad++ hoặc Notepad hoặc bất kỳ chương trình hỗ trợ gõ mã nào.  

### Khai báo
Sau khi mở tệp tin `TestSPS.ps1` lên, hãy khái báo (thiết lập môi trường) Selenium trong PowerShell.  
Thiết lập cho thư mục `SeleniumPowerShellTest`:  
```powershell
$workingPath = 'D:\SeleniumPowerShellTest'
```
Thiết lập môi trường để PowerShell có thể làm việc với Selenium, có 3 kiểu khác nhau, chọn cách nào cũng được:  
```powershell
Add-Type -Path "$($workingPath)\WebDriver.dll"
Add-Type -Path "$($workingPath)\WebDriver.Support.dll"
```  
```powershell
Import-Module "$($workingPath)\WebDriver.dll"
Import-Module "$($workingPath)\WebDriver.Support.dll"
```  
```powershell
[System.Reflection.Assembly]::LoadFrom("$($workingPath)\WebDriver.dll")
[System.Reflection.Assembly]::LoadFrom("$($workingPath)\WebDriver.Support.dll")
```  

### Tạo tùy chọn
Tùy chọn (options) cho trình duyệt khi cần dùng, không dùng thì không cần thêm vào.  
```powershell
$options = New-Object OpenQA.Selenium.Chrome.ChromeOptions
```  
```powershell
$options = New-Object OpenQA.Selenium.Firefox.FirefoxOptions
```  

Tùy chọn không hiển thị giao diện của trình duyệt.
```powershell
options.addArguments("--headless")
```   

Selenium sẽ không chạy trực tiếp trên trình duyệt Chrome hoặc Firefox đã được cài đặt. Vì vậy, cần tạo một phiên bản mới để Selenium làm việc.   
```powershell
$driver = New-Object OpenQA.Selenium.Chrome.ChromeDriver($options)
```  
```powershell
$driver = New-Object OpenQA.Selenium.Firefox.FirefoxDriver($options)
```  

Khởi tạo Implicit Wait. Ở đây là 29 giây chờ để trang/thành phần/vân vân tải hoàn tất.
```powershell
$driver.Manage().Timeouts().ImplicitWait = [TimeSpan]::FromSeconds(29)
```  

Lệnh Explicit Wait đơn giản, dễ dùng:
```powershell
Start-Sleep -Seconds 5
```  

### Khởi tạo trình duyệt
Để khởi động trình duyệt mới được chạy bởi Selenium thì chỉ cần sử dụng câu lệnh đơn giản:  
```powershell
$driver
```  
Nhưng thường được kết hợp bằng cách duyệt tới một địa chỉ cụ thể:
```powershell
$driver.Navigate().GoToURL('https://vegetaz.github.io')
```  

# Chạy
Để chạy được tệp tin PowerShell, cần mở PowerShell trong thư mục `SeleniumPowerShellTest`, hoặc sử dụng lệnh `cd` để đi đến. Gõ như bên dưới và nhấn `Enter` là được.
```powershell
.\TestSPS.ps1
```  

# Thoát
Sau khi truy cập đến đường dẫn đã được thiết lập và thực hiện các tệp lệnh đã được khai báo hoàn tất. Có thể tiến hành đóng/tắt/thoát trình duyệt.  
```powershell
$driver.Close()
```  
```powershell
$driver.Quit()
```  
```powershell
$driver.Dispose()
```  

**Đọc thêm**:
- [Selenium in PowerShell](https://www.google.com/search?q=Selenium+in+PowerShell&rlz=1C1PNBB_viVN954VN954&oq=Selenium+in+PowerShell&aqs=chrome..69i57j0i19i22i30l4j69i60l3.244j0j4&sourceid=chrome&ie=UTF-8)
