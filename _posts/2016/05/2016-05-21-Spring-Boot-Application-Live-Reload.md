---
layout: post
title: "Spring Boot Application Live Reload (Hot Swap) With IntelliJ IDEA"
date: 2016-05-21 14:32:04 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [spring]
img_path: /assets/img/SpringLiveReload/
---

**Spring Boot** cung cấp một `dependency` tải lại trực tiếp mà không cần khởi động lại cả chương trình:
```xml
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-devtools</artifactId>
            <optional>true</optional>
        </dependency>
```
Trong **IntelliJ IDEA**, mở **File** - > **Settings...** -> **Build, Execution, Deployment** -> **Compiler** và đảm bảo **Build project automatically** được kích hoạt.
![Build project automatically](Build-project-automatically.png)
_Build project automatically_

Nhấn tổ hợp phím **Ctrl + Shift + A** > **Registry...**, kích hoạt cấu hình sau:
```console
compiler.automake.allow.when.app.running
```
![compiler.automake.allow.when.app.running](compiler-automake-allow-when-app-running.png)
_compiler.automake.allow.when.app.running_

Khởi động lại **IntelliJ IDEA** là có thể sử dụng được!

**Đọc thêm**:
- [DZone](https://dzone.com/articles/spring-boot-application-live-reload-hot-swap-with)
- [stackoverflow](https://stackoverflow.com/questions/21399586/hot-swapping-in-spring-boot)
- [stackoverflow](https://stackoverflow.com/questions/40057057/spring-boot-and-thymeleaf-hot-swap-templates-and-resources-once-again)
