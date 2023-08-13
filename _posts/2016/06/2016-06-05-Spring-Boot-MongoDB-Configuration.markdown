---
layout: post
title: "Spring Boot Mongo DB Configuration with Properties File"
date: 2016-06-05 05:25:06 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [spring, database]
---

Khai báo `dependency` của **MongoDB** trong `pom.xml`:
```xml
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-data-mongodb</artifactId>
</dependency>
```

Cấu hình cho **MongoDB** ở tệp tin `application.properties`:
```properties
spring.data.mongodb.authentication-database=admin
spring.data.mongodb.username=root
spring.data.mongodb.password=root
spring.data.mongodb.database=local
spring.data.mongodb.port=27017
spring.data.mongodb.host=localhost
```

**Đọc thêm**:
- [MongoDB - The Developer Data Platform](https://www.mongodb.com/)