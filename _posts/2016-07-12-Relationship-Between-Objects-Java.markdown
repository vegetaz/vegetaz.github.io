---
layout: post
title: "Mối quan hệ giữa các đối tượng trong java"
date: 2016-06-25 15:25:10 +0700
categories: [java]
---

Bài này bạn và tôi sẽ đi tìm hiểu về mối quan hệ giữa các đối tượng trong Java.

## Quan hệ phụ thuộc
Quan hệ phụ thuộc là quan hệ mà đối tượng của lớp này sử dụng đối tượng của lớp kia. Ví dụ nếu trong lớp ClassA có sử dụng đối tượng của lớp ClassB (có thể là các thuộc tính, các tham số, các biến cục bộ, ...) thì lớp ClassA có quan hệ phụ thuộc với lớp ClassB.  
Ví dụ:
```java
class ClassA{
	public void myMethod(ClassB b) {
		b.doWork();
	}
}
```
Trong trường hợp trên lớp ClassA sẽ phụ thuộc vào lớp ClassB, nếu lớp ClassB thay đổi thì có thể lớp ClassA sẽ phải thay đổi theo.

Đây là quan hệ rộng nhất và được biểu diễn bằng mũi tên nét đứt giống như sau:
![Quan Hệ Phụ Thuộc](/static/img/posts/Quan_he_phu_thuoc.png)

## Quan hệ kết hợp (Association)
Quan hệ kết hợp xảy ra khi một đối tượng có thuộc tính là một đối tượng khác.  
Ví dụ: 
```java
class Employee {
	private String name;
	private Manager manager;

	public Employee(String name, Manager manager) {
		this.name = name;
		this.manager = manager;
	}

	public String getManagerName() {
		return manager.getName();
	}

	public String getName() {
		return name;
	}
}

class Manager {
	private String name;

	public Manager(String name) {
		this.name = name;
	}

	public String getName() {
		return name;
	}
}
```
Trong đoạn code trên lớp Employee có thuộc tính là đối tượng thuộc lớp Manager, do đó hai lớp này có quan hệ kết hợp. Quan hệ kết hợp được chia làm 2 loại là quan hệ thu nạp (Aggregation) và quan hệ hợp thành (Composition)

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