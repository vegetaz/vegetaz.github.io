---
layout: post
title: "Cài đặt Microsoft Sticky Notes trên Windows 10 LTSC"
date: 2016-07-16 15:25:10 +0700
categories: [Information Technology, Software]
tags: [windows]
img_path: /assets/img/StickyNotes/
---

Gần đây mình thích sử dụng Windows 10 Enterprise LTSC, vì sự nhẹ nhàng của nó.
Nhưng có một số vấn đề mình gặp, đó là nó không có sẵn Microsoft Store, cho nên mình không thể sử dụng một số ứng dụng có từ Store, tiêu biểu như là Sticky Notes.

Sticky Notes này của Microsoft có chức năng đồng bộ hoá các ghi chú của bạn, nên khi sử dụng ở máy tính Windows khác có cài Sticky Notes này, và đăng nhập tài khoản của bạn thì các ghi chú sẽ được đồng bộ.

Windows 10 LTSC của mình đang sử dụng có OS build là 17763.1, và là hệ điều hành sáu mươi tư bít.

### Tải về
Microsoft Sticky Notes hiện tại đang có tại cửa hàng, với đường dẫn là:
```url
https://www.microsoft.com/en-us/p/microsoft-sticky-notes/9nblggh4qghw
```
Bạn cần phải tải về và cài đặt các gói và phần mềm có liên quan để nó có thể hoạt động ngon lành với sợ hỗ trợ tải về của `rg-adguard`:
```url
https://store.rg-adguard.net/
```

### Cài đặt
Bạn có thể tải về và cài đặt toàn bộ các tệp tin đang hiển hiện, hoặc chỉ tải mỗi `Sticky Notes` về để cài đặt và có thông báo lỗi đến đâu thì khắc phục đến đó, hoặc thực hiện theo mình: 
```bash
Add-AppxPackage .\Microsoft.NET.Native.Framework.1.3_1.3.24211.0_x64__8wekyb3d8bbwe.Appx
Add-AppxPackage .\Microsoft.NET.Native.Framework.1.3_1.3.24211.0_x86__8wekyb3d8bbwe.Appx

Add-AppxPackage .\Microsoft.NET.Native.Framework.1.7_1.7.27413.0_x64__8wekyb3d8bbwe.Appx
Add-AppxPackage .\Microsoft.NET.Native.Framework.1.7_1.7.27413.0_x86__8wekyb3d8bbwe.Appx

Add-AppxPackage .\Microsoft.NET.Native.Framework.2.2_2.2.29512.0_x64__8wekyb3d8bbwe.Appx
Add-AppxPackage .\Microsoft.NET.Native.Framework.2.2_2.2.29512.0_x86__8wekyb3d8bbwe.Appx

Add-AppxPackage .\Microsoft.NET.Native.Runtime.1.4_1.4.24201.0_x64__8wekyb3d8bbwe.Appx
Add-AppxPackage .\Microsoft.NET.Native.Runtime.1.4_1.4.24201.0_x86__8wekyb3d8bbwe.Appx

Add-AppxPackage .\Microsoft.NET.Native.Runtime.1.7_1.7.27422.0_x64__8wekyb3d8bbwe.Appx
Add-AppxPackage .\Microsoft.NET.Native.Runtime.1.7_1.7.27422.0_x86__8wekyb3d8bbwe.Appx

Add-AppxPackage .\Microsoft.NET.Native.Runtime.2.2_2.2.28604.0_x64__8wekyb3d8bbwe.Appx
Add-AppxPackage .\Microsoft.NET.Native.Runtime.2.2_2.2.28604.0_x86__8wekyb3d8bbwe.Appx

Add-AppxPackage .\Microsoft.VCLibs.140.00_14.0.29231.0_x64__8wekyb3d8bbwe.Appx
Add-AppxPackage .\Microsoft.VCLibs.140.00_14.0.29231.0_x86__8wekyb3d8bbwe.Appx

Add-AppxPackage Microsoft.MicrosoftStickyNotes_3.7.142.0_neutral___8wekyb3d8bbwe.AppxBundle
```
Các câu lệnh trên thực hiện với PowerShell, chạy dưới quyền Administrator.

### Sử dụng
Để sử dụng thì rất đơn gian, gõ `Sticky Notes` để tìm kiếm từ thực đơn (menu) Start của Windows.
![Sticky Notes]({{ page.img_path }}Sticky-Notes.png)
_Sticky Notes_

**Đọc thêm**:
- [Notes](https://outlook.office.com/mail/notes)
