---
layout: post
title: "Lưu trữ thông tin đăng nhập của git trên ổ đĩa"
date: 2016-06-25 15:25:10 +0700
categories: [git]
---

Câu lệnh `git config --global credential.helper store` được sử dụng để cấu hình Git để lưu trữ thông tin xác thực (credentials) của người dùng (như tên người dùng và mật khẩu) trong một tệp tin cục bộ để tránh việc nhập lại thông tin xác thực mỗi lần người dùng thao tác với kho lưu trữ từ xa (remote repository).

Chi tiết về từng phần trong câu lệnh:
- `git config` là câu lệnh trong Git để cấu hình các tùy chọn và thiết lập trong Git.
- `--global` là tùy chọn để áp dụng cấu hình cho toàn bộ hệ thống Git của người dùng, không chỉ cho một kho lưu trữ cụ thể.
- `credential.helper` là một tùy chọn cấu hình trong Git để chỉ định trình trợ giúp (helper) xử lý thông tin xác thực.
- `store` là trình trợ giúp xử lý thông tin xác thực cho Git. Khi người dùng sử dụng trình trợ giúp này, Git sẽ lưu trữ thông tin xác thực của người dùng trong một tệp tin cục bộ không mã hóa trên máy tính của người dùng. Khi người dùng nhập thông tin xác thực lần đầu tiên, Git sẽ ghi nhớ và sử dụng nó cho các phiên làm việc tiếp theo mà không yêu cầu người dùng nhập lại.

Vậy câu lệnh `git config --global credential.helper store` là đang cấu hình Git để sử dụng trình trợ giúp "store" để lưu trữ thông tin xác thực. Điều này giúp người dùng tránh việc nhập lại thông tin xác thực mỗi khi người dùng thao tác với kho lưu trữ từ xa, giúp tiện lợi và tiết kiệm thời gian trong quá trình làm việc với Git. Tuy nhiên, hãy lưu ý rằng thông tin xác thực sẽ được lưu trữ dưới dạng văn bản không mã hóa, vì vậy hãy đảm bảo rằng tệp tin lưu trữ thông tin xác thực được bảo mật trên máy tính của người dùng.

Đọc thêm: [Helper to store credentials on disk](https://git-scm.com/docs/git-credential-store)  
