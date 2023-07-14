---
layout: post
title: "Spring Boot Mongo DB Configuration with Properties File"
date: 2016-06-05 05:25:06 +0700
categories: [spring, database]
---

Dĩ nhiên đầu tiên phải khai báo `dependency` của MongoDB trong `pom.xml` trước!
```xml
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-data-mongodb</artifactId>
</dependency>
```

Sau đó thì thực hiện cấu hình ở tệp tin `application.properties`
```properties
spring.data.mongodb.authentication-database=admin
spring.data.mongodb.username=root
spring.data.mongodb.password=root
spring.data.mongodb.database=local
spring.data.mongodb.port=27017
spring.data.mongodb.host=localhost
```
Các thông số mang tính chất tham khảo, các bạn cấu hình tuỳ chỉnh trên thiết bị của các bạn, đừng chỉ sao chép mà không chỉnh sửa!

Đó là cấu hình cho trường hợp có sử dụng quyền truy cập, trong trường hợp không cần thì có thể sử dụng cấu hình sau:
```properties
spring.data.mongodb.database=local
spring.data.mongodb.port=27017
spring.data.mongodb.host=localhost
```

**Nguồn**: Internet và bản thân!