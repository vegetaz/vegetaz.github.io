---
layout: post
title: "Upgrade all Python packages with pip in Windows"
date: 2025-07-11 08:41:25 +0700
categories: [Information Technology, Software]
tags: [windows, powershell]
---

Câu lệnh sau đây là lựa chọn hiệu quả hơn nếu bạn chỉ muốn cập nhật các gói Python được cài đặt bởi `pip` trên Windows. Câu lệnh nây sử dụng `pip list` và `pip install` cơ bản. Nó tránh lãng phí thời gian xử lý các gói đã ở phiên bản mới nhất.

---

Để cập nhật tất cả các gói Python đã cài đặt bằng **pip** trên Windows, bạn có thể sử dụng PowerShell. Dưới đây là hướng dẫn từng bước:
```powershell
(pip list --outdated --format=json | ConvertFrom-Json) | ForEach-Object { pip install --upgrade $_.name }
```
Câu lệnh này đảm bảo:
- Trích xuất chính xác tên gói.
- Chỉ nâng cấp các gói lỗi thời.
- Tránh lỗi do định dạng đầu ra.

**Đọc thêm**:
- [How to upgrade all Python packages with pip](https://stackoverflow.com/questions/2720014/how-to-upgrade-all-python-packages-with-pip)
