---
layout: post
title: "Hợp nhất trở lại định dạng ban đầu bằng Tikal"
date: 2022-01-18 16:06:10 +0700
categories: [Information Technology, Localization]
tags: [l10n, okapi, cat]
img_path: /assets/img/okapi/
---

Trên hệ điều hành Windows, mở thư mục [Okapi](https://vegetaz.github.io/posts/Okapi-Framework/), chạy tệp tin **startTikalPrompt.bat** để khởi động chương trình **Tikal** trong môi trường dòng lệnh.

> Tính năng này của [Tikal](https://vegetaz.github.io/posts/Tikal/) chỉ làm việc với định dạng tệp tin `.xlf` do Tikal tạo ra bằng lệnh [`-x`](https://vegetaz.github.io/posts/Use-Tikal-to-create-XLF/) (Extract Files).
{:.prompt-info}

Lệnh này hợp nhất trở lại định dạng ban đầu của một hoặc nhiều tài liệu [XLIFF](https://vegetaz.github.io/posts/XLIFF/).
```shell
tikal -m "Liên_kết_tới_tệp_tin_XLIFF_được_tạo_ra_bởi_Tikal.xlf" -fc "Liên_kết_tới_tệp_tin_Filter_Configuration.fprm"
```
Trong đó:
- `-m` có nghĩa là hợp nhất (merge) trở lại định dạng ban đầu
- `-fc` có nghĩa là Filter Configuration

Sau khi câu lệnh được thực thi thì tệp tin `.out.định_dạng_ban_đầu` sẽ được đặt tại thư mục chứa tệp tin `.xlf`.

Không nhất thiết sử dụng các tuỳ chọn `-fc` trong quá trình hợp nhất nếu tệp tin `.xlf` được tạo ra bằng cách áp dụng các `Filter Configuration` mặc định của [Rainbow](https://vegetaz.github.io/posts/Rainbow/).

**Xem thêm**:
- [Tikal](https://vegetaz.github.io/posts/Tikal/)
- [Merge Files](https://okapiframework.org/wiki/index.php/Tikal_-_Extraction_Commands#Merge_Files)
