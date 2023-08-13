---
layout: post
title: "Cấu hình Sublime Text để chạy Java"
date: 2016-04-19 19:19:21 +0700
categories: [Information Technology]
tags: [editor, java, others]
---

### Công cụ cần thiết

1. [Sublime Text 3](https://www.sublimetext.com/3)
2. [7-Zip](https://www.7-zip.org/)

### Thiết lập Sublime Text

1. Mở 7-Zip File Manager với quyền Administrator<br/>
   ![](/static/img/posts/7-Zip-File-Manager.png)
2. Truy cập đến nơi chứa Packages của Sublime Text, đây là của mình trên Windows 10:<br/>
   ![](/static/img/posts/7-Zip-File-Manager-Open.png)
3. Chọn `Java.sublime-package` và nhấn chuột phải, chọn Open thì sẽ được như hình:<br/>
   ![](/static/img/posts/7-Zip-File-Manager-Open-2.png)
4. Chọn `JavaC.sublime-build` và nhấn chuột phải, chọn Edit sẽ được như hình:<br/>
   ![](/static/img/posts/7-Zip-File-Manager-Open-3.png)
5. Thay thế với đoạn code dưới đây:

```json
{
	"cmd": ["runJava.bat", "$file"],
	"file_regex": "^(...?):([0-9]):?([0-9]*)",
	"selector": "source.java",
	"shell": true
}
```

6. Lưu lại:<br/>
   ![](/static/img/posts/7-Zip-File-Manager-Open-4.png)
7. Tiếp tục tạo thêm tệp tin `runJava.bat` với nội dung như sau:<br/>

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

8. Cho tệp tin đó vào thư mục `bin` của JDK:<br/>
   ![](/static/img/posts/Run-Java-Bin.PNG)
9. Thiết lập như sau khi sử dụng:<br/>
   ![](/static/img/posts/JavaC.png)
10. Kết quả:<br/>
    ![](/static/img/posts/Java-in-Sublime.PNG)

<br/>
Như vậy là mình đã thiết lập thành công Sublime Text 3 để chạy Java.
Các bạn có góp ý gì hãy để lại comment phía bên dưới nhé!
