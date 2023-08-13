---
layout: post
title: "Spring Boot Application Live Reload (Hot Swap) With IntelliJ IDEA"
date: 2016-05-21 14:32:04 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [spring]
img_path: /assets/img/SpringLiveReload/
---

Trong quá trình viết mã, phát triển ứng dụng sử dụng Spring Boot bằng IntelliJ IDEA, thật khó chịu khi phải chạy lại cả chương trình Spring Boot cồng kềnh sau mỗi thay đổi.  
Spring Boot cung cấp tải lại trực tiếp mà không cần khởi động lại cả chương trình. Chỉ cần thêm:

```xml
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-devtools</artifactId>
            <optional>true</optional>
        </dependency>
```

Nhưng nó vẫn chưa hoạt động, cần phải tinh chỉnh thêm một số thao tác khác trong IntelliJ IDEA.  
Đầu tiên, mở **File** - > **Settings...** -> **Build, Execution, Deployment** -> **Compiler** và đảm bảo **Build project automatically** được kích hoạt.  
![Build project automatically](Build-project-automatically.png)

Tiếp theo, nhấn tổ hợp phím Ctrl + Shift + A để tìm kiếm Registry...  
Trong Registry, kích hoạt cấu hình sau:

```
compiler.automake.allow.when.app.running
```

![](compiler-automake-allow-when-app-running.png)

Khởi động lại IDEA và trải nghiệm!

**Đọc thêm**:
- [DZone](https://dzone.com/articles/spring-boot-application-live-reload-hot-swap-with)
- [stackoverflow](https://stackoverflow.com/questions/21399586/hot-swapping-in-spring-boot)
- [stackoverflow](https://stackoverflow.com/questions/40057057/spring-boot-and-thymeleaf-hot-swap-templates-and-resources-once-again)
