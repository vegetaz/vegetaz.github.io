---
layout: post
title: "Tạo tệp tin XLF bằng Tikal"
date: 2022-01-08 16:06:10 +0700
categories: [Information Technology, Localization]
tags: [l10n, okapi, cat]
img_path: /assets/img/okapi/
---

Trên hệ điều hành Windows, mở thư mục [Okapi](https://vegetaz.github.io/posts/Okapi-Framework/), chạy tệp tin **startTikalPrompt.bat** để khởi động chương trình **Tikal** trong môi trường dòng lệnh.

Để tạo tệp tin [XLIFF](https://vegetaz.github.io/tags/okapi/) từ các tệp tin được Tikal hỗ trợ, sử dụng cấu trúc câu lệnh:
```shell
tikal -x "Đường_dẫn_tới_tệp_tin_nguồn_cần_tạo_thành_tệp_tin_XLIFF.xlxs" -fc "Đường_dẫn_tới_tệp_tin_Filter_Configuration_tuỳ_chỉnh.fprm" -sl en-US -tl vi-VN -oe UTF-8
```
Trong đó:
- `-x` có nghĩa là giải nén tệp tin (Extract Files), có thể được hiểu là Tikal thực hiện trích xuất dữ liệu cần được bản địa hoá từ tệp tin nguồn.
- `-fc` có nghĩa là mã định danh của cấu hình bộ lọc (Filter Configuration) sẽ sử dụng để trích xuất. Lựa chọn này tuỳ chọn. Nếu không sử dụng thì Tikal sẽ sử dụng một cấu hình bộ lọc có sẵn trong Rainbow của Okapi. Nếu sử dụng cấu hình bộ lọc tuỳ chỉnh thì cần cung cấp liên kết tới cấu hình bộ lọc đó.
- `-sl` có nghĩa là ngôn ngữ nguồn (Source Language).
- `-tl` có nghĩa là ngôn ngữ bản địa (Target Language).
- `-oe` có nghĩa là mã hoá của tệp tin bản địa (Output Encoding)

Sau khi câu lệnh được thực thi thì tệp tin `.xlf` sẽ được đặt tại thư mục chứa tệp tin nguồn.

![Extract Files](Tikal_x.png)
_Extract Files_

**Xem thêm**:
- [Tikal - Okapi Framework](https://okapiframework.org/wiki/index.php?title=Tikal)
