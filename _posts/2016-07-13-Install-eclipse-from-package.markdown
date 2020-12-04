---
layout: post
title: "Tải về và cài đặt eclipse trên Ubuntu"
date: 2016-06-25 15:25:10 +0700
categories: [linux, ubuntu, others]
---

Đây là cách sử dụng Eclipse IDE for Enterprise Java Developers bằng cách download package từ [trang chủ eclipse](https://www.eclipse.org/downloads/packages/).

## Tải về
Truy cập vào trang chủ eclipse, lựa chọn phiên bản phù hợp, ở đây mình lựa chọn Eclipse IDE for Enterprise Java Developers, tiếp theo là gói phù hợp cho hệ điều hành, lựa chọn của mình trong trường hợp này là `Linux x86_64`.  
![Download eclipse](/static/img/install-eclipse/Download_eclipse.png)

### Quan hệ thu nạp (Aggregation)
Quan hệ thu nạp xảy ra khi một đối tượng có thuộc tính là một đối tượng khác và 2 đối tượng này có thể tồn tại độc lập.  
Ví dụ:
```java
public class ClassA {       
    ClassB b;
    public void setB(ClassB b){
    	this.b = b;
     }
}
```
Có thể thấy đối tượng của ClassB tồn tại độc lập với đối tượng của ClassA (ClassA không tạo ra đối tượng của ClassB).
![Quan Hệ Thu Nạp](/static/img/posts/Aggregation.png)

### Quan hệ hợp thành (Composition)
Quan hệ hợp thành xảy ra khi đối tượng của lớp ClassB là 1 phần trong đối tượng của lớp ClassA, khi đối tượng của lớp ClassA bị hủy thì đối tượng của ClassB cũng bị hủy theo. Ví dụ mối quan hệ giữa File và Folder, một Folder sẽ có nhiều File và nếu Folder bị hủy thì File cũng bị hủy theo. Quan hệ hợp thành này sẽ được biểu diễn dưới sơ đồ lớp như sau:
![Quan Hệ Hợp Thành](/static/img/posts/Composition.png)


Số 1 và ký tự * thể hiện rằng 1 Folder sẽ có nhiều File. Nếu nói tới code thì khi một đối tượng được tạo ra trong một đối tượng khác thì đó là quan hệ hợp thành:
```java
public class ClassA{
	private ClassB b;
	public ClassA() {
		b = new ClsasB();
	}
}
```
Đọc tới đây bạn đã hiểu về các quan hệ giữa các đối tượng chưa?  
Còn tôi thì vẫn lơ tơ mơ lắm! :3