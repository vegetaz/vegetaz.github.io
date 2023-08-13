---
layout: post
title: "Cấu hình Sublime Text để chạy Java"
date: 2016-04-19 19:19:21 +0700
categories: [Information Technology]
tags: [editor, java, others]
img_path: /assets/img/SublimeJava/
---

### Công cụ cần thiết
- [Sublime Text 3](https://www.sublimetext.com/3)
- [7-Zip](https://www.7-zip.org/)

### Thiết lập Sublime Text
Mở 7-Zip File Manager với quyền Administrator<br/>
![](7-Zip-File-Manager.png)

Truy cập đến nơi chứa Packages của Sublime Text, đây là của mình trên Windows 10:<br/>
![](7-Zip-File-Manager-Open.png)

Chọn `Java.sublime-package` và nhấn chuột phải, chọn Open thì sẽ được như hình:<br/>
![](7-Zip-File-Manager-Open-2.png)

Chọn `JavaC.sublime-build` và nhấn chuột phải, chọn Edit sẽ được như hình:<br/>
![](7-Zip-File-Manager-Open-3.png)

Thay thế với đoạn code dưới đây:
```json
{
	"cmd": ["runJava.bat", "$file"],
	"file_regex": "^(...?):([0-9]):?([0-9]*)",
	"selector": "source.java",
	"shell": true
}
```
Lưu lại:<br/>
![](7-Zip-File-Manager-Open-4.png)

Tiếp tục tạo thêm tệp tin `runJava.bat` với nội dung như sau:<br/>
```bat
@ECHO OFF
cd %~dp1
ECHO %~nx1 
IF EXIST %~n1.class (
DEL %~n1.class
)
javac -encoding utf8 %~nx1
IF EXIST %~n1.class (
ECHO OFF
java -Dfile.encoding=UTF8 %~n1
ECHO OFF
)
```

Cho tệp tin đó vào thư mục `bin` của JDK:<br/>
![](Run-Java-Bin.PNG)

Thiết lập như sau khi sử dụng:<br/>
![](JavaC.png)

### Kết quả
![](Java-in-Sublime.PNG)

[Java in Sublime Text](https://www.google.com/search?q=java+in+sublime+text&rlz=1C1PNBB_viVN954VN954&oq=java+in+sublime+text&aqs=chrome.0.0i19i512j0i19i22i30l3j69i65l2.6576j0j4&sourceid=chrome&ie=UTF-8)
