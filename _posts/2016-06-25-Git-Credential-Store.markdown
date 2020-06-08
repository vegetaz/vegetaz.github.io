---
layout: post
title: "Lưu trữ thông tin đăng nhập của git trên ổ đĩa"
date: 2016-06-25 15:25:10 +0700
categories: [git]
---

Trong một số trường hợp sử dụng git, github các bạn sẽ gặp trường hợp đó là đã nhập tên đăng nhập và mật khẩu rồi. Nhưng một lát sau đó, git sẽ vẫn sẽ hỏi lại khi bạn thực hiện pull hoặc push hoặc vân vân, mây mây...

Mình có gặp trường hợp này khi sử dụng hệ điều hành Ubuntu.

Sau 3,14 phút tìm kiếm trên Google mình đã thấy hướng dẫn lưu trữ thông tin đăng nhập trên trang chủ của git.

Thật vi diệu!

Sử dụng trình trợ giúp này sẽ lưu trữ mật khẩu của bạn mà không được mã hoá, chỉ được bảo vệ bởi các quyền truy cập của hệ thống.

Đó là những gì trên git-scm đã nói.

Theo kinh nghiệm của mình thì bạn nên sử dụng câu lệnh dưới đây trước khi nhập tên đăng nhập và mật khẩu:
```git
git config --global credential.helper store
```

Có thể liệt kê ra các cấu hình cho git của bạn với câu lệnh:
```git
git config --global --list
```

Như vậy, chỉ cần với `credential.helper store` thì thông tin đăng nhập của bạn đã được lưu trữ trên ổ đĩa.
Thông tin tham khảo thêm:
https://git-scm.com/docs/git-credential-store

Chúc may mắn!
