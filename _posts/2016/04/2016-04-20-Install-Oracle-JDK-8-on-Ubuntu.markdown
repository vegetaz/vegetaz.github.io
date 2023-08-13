---
layout: post
title: "Cài đặt Oracle JDK-8 trên Ubuntu"
date: 2016-04-20 09:41:20 +0700
categories: [Information Technology, Software]
tags: [java, linux, ubuntu]
---

Đầu tiên, tạo 1 thư mục `jvm` hoặc `jdk` với câu lệnh như sau:
```bash
sudo mkdir /usr/lib/jvm/
```

Tiếp theo, là tải về gói `jdk` từ trang của Oracle, chọn gói `tar.gz`.
Ví dụ: `jdk-8u231-linux-x64.tar.gz`
```bash
sudo tar -zxvf jdk-8u231-linux-x64.tar.gz -C /usr/lib/jvm/
```

Cài đặt
```bash
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk1.8.0_231/bin/java 3
```
```bash
sudo update-alternatives --config java
```

```bash
java version "1.8.0_231"
Java(TM) SE Runtime Environment (build 1.8.0_231-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.231-b11, mixed mode)
```

Bước tiếp theo là thiết lập môi trường làm việc cho Java.
Để thực hiện, tạo 1 tệp tin `sh` trong `/etc/profile.d` với lệnh sau:
```bash
sudo nano /etc/profile.d/javajdk.sh
```

Ubuntu sẽ mở tệp tin `sh` đó bằng chương trình `nano`:
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

Chỉ cần kiểm tra bằng câu lệnh `javac -version` nữa là đủ:
```console
javac 1.8.0_231
```

> Tham khảo <https://vegetaz.github.io/posts/java-in-linux-mint/> để cài đặt JDK nhanh chóng, thuận tiện hơn.
{:.prompt-info}
