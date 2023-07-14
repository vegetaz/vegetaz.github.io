---
layout: post
title: "Cài đặt Oracle JDK-8 trên Ubuntu"
date: 2016-04-20 09:41:20 +0700
categories: [java, linux, ubuntu]
---

Ubuntu này là Subsytem trên Windows nhé các bạn. Mục đích sử dụng Ubuntu của mình không có nhiều nên mình không cài Ubuntu như một hệ điều hành riêng biệt mà tận dụng của Windows 10 luôn.

Đầu tiên, các bạn tạo 1 thư mục `jvm` hoặc `jdk` với câu lệnh như sau:

```bash
sudo mkdir /usr/lib/jvm/
```

Tiếp theo, là tải về gói `jdk` từ trang của Oracle, các bạn nhớ chọn gói `tar.gz` nhé.
Ở đây mình chọn gói `jdk-8u231-linux-x64.tar.gz`

Tại thư mục mà gới `jdk` được tải về, các bạn tiến hành xả nén và sao chép với câu lệnh bên dưới

```bash
sudo tar -zxvf jdk-8u231-linux-x64.tar.gz -C /usr/lib/jvm/
```

Và cài đặt

```bash
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk1.8.0_231/bin/java 3
```

Số `3` có thể thay bằng bất kỳ số nào bạn thích. Lúc này hệ thống `wsl` của mình chưa có phiên bản Java nào được cài nên con số này không ảnh hưởng gì nhiều.

Nếu bạn đã cài nhiều phiên bản Java khác, hãy tiến hành cấu hình với câu lệnh sau:

```bash
sudo update-alternatives --config java
```

Kiểm tra phiên bản Java với câu lệnh `java -version` sẽ cho ra kết quả như bên dưới là thành công

```bash
java version "1.8.0_231"
Java(TM) SE Runtime Environment (build 1.8.0_231-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.231-b11, mixed mode)
```

Bước tiếp theo là thiết lập môi trường làm việc cho Java.
Để thực hiện, các bạn tạo 1 tệp tin `sh` trong `/etc/profile.d` với lệnh sau:

```bash
sudo nano /etc/profile.d/javajdk.sh
```

Ubuntu sẽ mở tệp tin `sh` đó bằng chương trình `nano`, các bạn có thể tham khảo thiết lập của mình

```bash
export PATH=$PATH:/usr/lib/jvm/jdk1.8.0_231/bin
export JAVA_HOME=/usr/lib/jvm/jdk1.8.0_231/
export JRE_HOME=/usr/lib/jvm/jdk1.8.0_231/jre/
export J2SDKDIR=/usr/lib/jvm/jdk1.8.0_231/
export J2REDIR=/usr/lib/jvm/jdk1.8.0_231/jre/
```

Lưu lại và thoát khỏi `nano`, chạy câu lệnh tiếp theo để hoàn tất:

```bash
source /etc/profile.d/javajdk.sh
```

Giờ chỉ cần kiểm tra bằng câu lệnh `javac -version` nữa là đủ.

```bash
javac 1.8.0_231
```

Thế là xong!
