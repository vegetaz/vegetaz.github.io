---
layout: post
title: "Tạo Filter Configuration trong Rainbow"
date: 2022-01-05 16:06:10 +0700
categories: [Information Technology, Localization]
tags: [l10n, okapi, cat]
img_path: /assets/img/okapi/
---

Mặc định Okapi Framework đã có một số [Filter](https://okapiframework.org/wiki/index.php/Filters) cho các phần mềm/công cụ trực thuộc, người dùng có thể tùy chỉnh/tạo mới Filter Configuration dựa vào những Filter Configuration đã có.

Từ cửa sổ của phần mềm Rainbow, chọn **Tool**, chọn **Filter Configuration...**, cửa sổ Filter Configuration mở lên.
![Filter Configuration...](Rainbow_Tools.png)
_Filter Configuration..._

Trong cửa số Filter Configuration, chọn một Filter Configuration bất kỳ, nhấn **Create...**.
![Filter Configurations](Filter_Configurations.png)
_Filter Configurations_

Cửa sổ tạo tên mới cho Filter Configuration được mở lên, tên mới này bao gồm tiền tố là ID của Filter Configuration mà người dùng đã chọn, kết nối với tên mới bằng ký tự `@`.
![Create Configuration](Create_Configuration.png)
_Create Configuration_
Nhấn OK để đặt tên mới.

Cửa sổ tùy chọn cho Filter Configuration mới được mở lên.
![Office 2007 Filter Parameters](Office_2007_Filter_Parameters.png)
_Office 2007 Filter Parameters_

Tại đây người dùng có thể tiến hành thêm, bớt các tùy chọn phù hợp cho nhu cầu sử dụng.
![Office 2007 Filter Parameters General Options](Office_2007_Filter_Parameters_General_Options.png)
_Office 2007 Filter Parameters General Options_

![Office 2007 Filter Parameters Word Options](Office_2007_Filter_Parameters_Word_Options.png)
_Office 2007 Filter Parameters Word Options_

![Office 2007 Filter Parameters Powerpoint Options](Office_2007_Filter_Parameters_Powerpoint_Options.png)
_Office 2007 Filter Parameters Powerpoint Options_

![](Office_2007_Filter_Parameters_Excel_Options.png)
_Office 2007 Filter Parameters Excel Options_

![New Filter Configurations](Filter_Configurations_After.png)
_New Filter Configurations_

Filter Configuration mới này sẽ được lưu tại thư mục `C:\Users\%username%\` với tên mà người dùng đã đặt.

**Xem thêm**:
- [Rainbow](https://vegetaz.github.io/posts/Rainbow/)
- [Rainbow - Okapi Framework](https://okapiframework.org/wiki/index.php/Rainbow)
