---
layout: post
title: "Tạo tệp tin TMX từ XLF bằng Tikal"
date: 2022-01-08 16:06:10 +0700
categories: [Information Technology, Localization]
tags: [l10n, okapi, cat]
img_path: /assets/img/okapi/
---

Trên hệ điều hành Windows, mở thư mục [Okapi](https://vegetaz.github.io/posts/Okapi-Framework/), chạy tệp tin **startTikalPrompt.bat** để khởi động chương trình **Tikal** trong môi trường dòng lệnh.

Để tạo tệp tin [TMX](https://vegetaz.github.io/posts/TMX/) từ các tệp tin được [Tikal](https://vegetaz.github.io/posts/Tikal/) hỗ trợ (trong trường hợp này là [XLIFF](https://vegetaz.github.io/posts/XLIFF/)), sử dụng cấu trúc câu lệnh:
```shell
tikal -2tmx "Đường_dẫn_tới_tệp_tin_nguồn_cần_tạo_thành_tệp_tin_TMX.xlf" -sl en-US -tl vi-VN
```
Trong đó:
- `-2tmx` có nghĩa là huyển đổi sang định dạng TMX (convert to table format)
- `-sl` có nghĩa là ngôn ngữ nguồn (source language)
- `-tl` có nghĩa là ngôn ngữ bản địa (target language)

Sau khi câu lệnh được thực thi thì tệp tin `.tmx` sẽ được đặt tại thư mục chứa tệp tin `.xlf`.

Không nhất thiết sử dụng các tuỳ chọn `-sl` và `-tl` trong quá trình chuyển đổi nếu trong tệp tin `.xlf` đã khai báo ngôn ngữ nguồn và ngôn ngữ bản địa.

**Xem thêm**:
- [Tikal](https://vegetaz.github.io/posts/Tikal/)
- [Convert to TMX Format](https://okapiframework.org/wiki/index.php/Tikal_-_Conversion_Commands#Convert_to_TMX_Format)
