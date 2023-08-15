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
tikal -x "Đường_dẫn_tới_tệp_tin_nguồn_cần_tạo_thành_tệp_tin_XLIFF.xlxs" -fc "Đường_dẫn_tới_tệp_tin_Filter_Configuration_tuỳ_chỉnh.fprm" -sl en-US -tl fr-FR -oe UTF-8
```

**Xem thêm**:
- [Tikal - Okapi Framework](https://okapiframework.org/wiki/index.php?title=Tikal)
- [Okapi Framework](https://vegetaz.github.io/posts/Okapi-Framework/)
