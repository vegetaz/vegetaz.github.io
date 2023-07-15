---
layout: post
title: "Cách sử dụng phương thức getFullPageScreenshotAs trong PowerShell"
date: 2020-12-10 16:06:10 +0700
categories: [selenium, powershell]
---

Phương thức (medthod) `getFullPageScreenshotAs` ra đời ngày 22 tháng 9 năm 2021 ở phiên bản Selenium 4. Nó cho phép WebDriver chụp ảnh toàn bộ trang web, bao gồm cả các phần không hiển thị trên màn hình. Phương thức này có thể hữu ích để xác minh rằng toàn bộ trang web đang hoạt động như mong đợi, hoặc để ghi lại lỗi khi điều hướng đến một trang web.  
Cú pháp của phương thức `getFullPageScreenshotAs` trong PowerShell như sau:
```powershell
$screenshot = $driver.GetFullPageScreenshot()
```  
Phương thức này trả về một đối tượng (File) đại diện cho ảnh chụp màn hình của trang web dưới dạng Base64. Bạn có thể lưu ảnh chụp màn hình vào ổ đĩa cục bộ bằng cách sử dụng phương thức `WriteAllBytes()`.
```powershell
$screenshotBase64 = $screenshot.AsBase64EncodedString
[System.IO.File]::WriteAllBytes("file_name_with_path.png", [System.Convert]::FromBase64String($screenshotBase64))
```  
Thông tin đọc thêm: [Interface HasFullPageScreenshot](https://www.selenium.dev/selenium/docs/api/java/org/openqa/selenium/firefox/HasFullPageScreenshot.html#getFullPageScreenshotAs(org.openqa.selenium.OutputType)).
