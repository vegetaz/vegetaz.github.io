---
layout: post
title: "Kiểm thử tự động ứng dụng trên Windows với WinAppDriver"
date: 2023-08-03 14:32:01 +0700
categories: [Information Technology, Software]
tags: [windows, selenium]
---

Trình điểu khiển ứng dụng Windows (**WinAppDriver**) là một dịch vụ (service) hỗ trợ tự động kiểm thử giao diện (UI Test Automation) giống như Selenium trên các ứng dụng Windows. Dịch vụ này hỗ trợ kiểm thử các ứng dụng Universal Windows Platform (UWP), Windows Forms (WinForms), Windows Presentation Foundation (WPF), và Classic Windows (Win32) chạy trên máy tính Windows 10.

---

#### Cài đặt và chạy WinAppDriver
1. Tải về chương trình cài đặt Windows Application Driver từ <https://github.com/Microsoft/WinAppDriver/releases>
2. Chạy trình cài đặt trên máy tính Windows 10 nơi ứng dụng đang kiểm tra được cài đặt và sẽ được kiểm tra
3. Kích hoạt chế độ [Developer Mode](https://docs.microsoft.com/en-us/windows/uwp/get-started/enable-your-device-for-development) trong cài đặt của Windows
4. Chạy `WinAppDriver.exe` từ thư mục cài đặt (E.g. `C:\Program Files (x86)\Windows Application Driver`)

Windows Application Driver sẽ chạy trên máy tính kiểm thư và lắng nghe các yêu cầu trên địa chỉ IP và cổng mặc đinh (`127.0.0.1:4723`). Có thể chạy bất kỳ ứng dụng cần kiểm thử nào [Tests](/Tests/) hoặc [Samples](/Samples). `WinAppDriver.exe` có thể được cấu hình lại địa chỉ IP và cổng lắng nghe, ví dụ:

```powershell
WinAppDriver.exe 4727
WinAppDriver.exe 10.0.0.10 4725
WinAppDriver.exe 10.0.0.10 4723/wd/hub
```

> **Lưu ý**: Ứng dụng `WinAppDriver.exe` cần phải chạy với tư cách **Quản trị (Administrator)** để có thể thấy được địa chỉ IP (IP address) và cổng (port).

Đọc thêm: [**Windows Application Driver**](https://github.com/microsoft/WinAppDriver)
