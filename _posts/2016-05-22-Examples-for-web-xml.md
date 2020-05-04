---
layout: post
title: "Một số mẫu tham khảo cho web.xml"
date: 2016-05-22 04:04:23 +0700
categories: [web, spring]
---

`web.xml` là tệp để cấu hình mô tả triển khai mô hình web trong servlet.

![web.xml](/static/img/_posts/web.xml-jsp-servlet.png)

Dưới đây là một số mẫu cấu hình `web.xml` với mục đích tham khảo.

**Servlet 4.0**<br/>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://xmlns.jcp.org/xml/ns/javaee" xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_4_0.xsd" id="WebApp_ID" version="4.0">
  <display-name>Vận Già 4.0</display-name>
</web-app>
```

**Servlet 3.1**<br/>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://xmlns.jcp.org/xml/ns/javaee" xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd" id="WebApp_ID" version="3.1">
	<display-name>Vận Già 3.1</display-name>
	<welcome-file-list>
		<welcome-file>index.jsp</welcome-file>
	</welcome-file-list>
</web-app>
```

**Servlet 3.0**<br/>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns="http://java.sun.com/xml/ns/javaee" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_3_0.xsd" version="3.0">
</web-app>
```

**Servlet 2.5**<br/>

```xml
<web-app xmlns="http://java.sun.com/xml/ns/javaee" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd" version="2.5">
</web-app>
```

**Servlet 2.4**<br/>

```xml
<web-app xmlns="http://java.sun.com/xml/ns/j2ee" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://java.sun.com/xml/ns/j2ee http://java.sun.com/xml/ns/j2ee/web-app_2_4.xsd" version="2.4">

  <display-name>Vận Già 2.4</display-name>
</web-app>
```

**Servlet 2.3**<br/>

```xml
<!DOCTYPE web-app PUBLIC "-//Sun Microsystems, Inc.//DTD Web Application 2.3//EN" "http://java.sun.com/dtd/web-app_2_3.dtd" >

<web-app>
  <display-name>Vận Già 2.3</display-name>
</web-app>
```

**Nguồn**: [Java servlet](https://en.wikipedia.org/wiki/Java_servlet)
