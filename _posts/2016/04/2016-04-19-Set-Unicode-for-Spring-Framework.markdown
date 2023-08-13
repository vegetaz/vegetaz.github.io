---
layout: post
title: "Hiển thị tiếng Việt trong Spring Framework"
date: 2016-04-19 14:39:34 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [spring, java]
---

```xml
     <filter>
        <filter-name>encoding-filter</filter-name>
        <filter-class>
            org.springframework.web.filter.CharacterEncodingFilter
        </filter-class>
        <init-param>
            <param-name>encoding</param-name>
            <param-value>UTF-8</param-value>
        </init-param>
        <init-param>
            <param-name>forceEncoding</param-name>
            <param-value>true</param-value>
        </init-param>
     </filter>
     <filter-mapping>
        <filter-name>encoding-filter</filter-name>
        <url-pattern>/*</url-pattern>
     </filter-mapping>
```
