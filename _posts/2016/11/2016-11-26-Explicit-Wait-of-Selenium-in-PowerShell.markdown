---
layout: post
title: "Explicit Wait của Selenium trong PowerShell"
date: 2016-11-26 11:11:11 +0700
categories: [Information Technology, Testing]
tags: [selenium, powershell]
---

Explicit wait là một loại chờ (wait) trong Selenium cho phép bạn chỉ định một khoảng thời gian chờ và một điều kiện để WebDriver đợi trước khi đưa ra ngoại lệ. Điều này trái ngược với implicit wait, trong đó WebDriver sẽ đợi một khoảng thời gian nhất định trước khi đưa ra ngoại lệ, bất kể điều kiện nào.  

Explicit wait thường được sử dụng khi bạn cần đợi một phần tử trên trang web trở nên có thể tương tác hoặc khi bạn cần đợi một sự kiện cụ thể xảy ra.  

Để sử dụng explicit wait, bạn có thể sử dụng phương thức WebDriverWait.until(). Phương thức này có hai tham số:  

Tham số đầu tiên là một điều kiện mà bạn muốn WebDriver đợi. Điều kiện này có thể là bất kỳ biểu thức nào trả về giá trị Boolean.  
Tham số thứ hai là khoảng thời gian mà bạn muốn WebDriver đợi, tính bằng mili giây.  

Nếu điều kiện được đáp ứng trước khi hết thời gian chờ, thì phương thức WebDriverWait.until() sẽ trả về kết quả của điều kiện. Nếu điều kiện không được đáp ứng trước khi hết thời gian chờ, thì phương thức sẽ đưa ra ngoại lệ.

Dưới đây là một ví dụ về cách sử dụng explicit wait để đợi một phần tử hiển thị ra để có thể tương tác:  

```powershell
$wait = New-Object OpenQA.Selenium.Support.UI.WebDriverWait($driver, [TimeSpan]::FromMilliseconds(1000))
$condition = {
    param($driver)
    $element = $driver.FindElement([OpenQA.Selenium.By]::ID('myButton'))
        if ($element.Displayed) {
            return $true
        } else {
            return $false
        }
    }

# Wait for the element to be displayed
$wait.Until([System.Func[Object,Boolean]]$condition) | Out-Null

# Perform some action on the element
$element = $driver.FindElement([OpenQA.Selenium.By]::ID('myButton'))
$element.Click()
```  

Trong ví dụ này, tôi đang sử dụng explicit wait để đợi một phần tử có ID là "myButton" hiển thị ra để có thể tương tác. Nếu phần tử hiển thị ra để có thể tương tác trong vòng 1000 mili giây, thì phương thức WebDriverWait.until() sẽ trả về phần tử. Nếu phần tử không hiển thị ra để có thể tương tác trong vòng 1000 mili giây, thì phương thức sẽ đưa ra ngoại lệ.  

Ngoài ra, trong PowerShell có thể sử dụng câu lệnh `Start-Sleep -Seconds 1` để thay thế cho explicit wait một cách nhanh chóng và tiện lợi.  

Explicit wait là một công cụ mạnh mẽ có thể giúp bạn viết các bài kiểm tra Selenium đáng tin cậy hơn. Bằng cách sử dụng explicit wait, bạn có thể đảm bảo rằng các bài kiểm tra của bạn sẽ không thất bại chỉ vì một phần tử trên trang web chưa được tải hoặc một sự kiện chưa xảy ra.  
