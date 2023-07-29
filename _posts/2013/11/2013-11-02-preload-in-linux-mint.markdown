---
layout: post
title: "Cài đặt Preload cho Linux Mint"
date: 2013-11-02 07:08:09 +0700
categories: [linux]
---

### Preload là gì?
Preload là một ứng dụng daemon (không phải yêu tinh, không phải ác quỷ, chỉ là cái tên thôi, nó là một chương trình không có giao diện) chạy ngầm trên hệ thống. Nó sẽ phân tích hành vi của người dùng và theo dõi những ứng dụng/phần mềm nào được người dùng thường xuyên sử dụng. Dựa trên các phân tích này, nó sẽ dự đoán ứng dụng nào người dùng dự tính mở và tải trước một phần vào RAM, đến khi người dùng cần khởi động sẽ không phải đợi lâu. Đó là cách mà Preload cải thiện tốc độ hệ thống.  

### Cài đặt
Mở cửa sổ Terminal lên và gõ lệnh:  
```shell
sudo apt-get install preload
```  

Preload không cần cấu hình, nó tự làm tất cả những gì cần thiết.  
Sau khi khởi động lại, nó sẽ bắt đầu chạy ở chế độ nền và dần cải thiện tốc độ ứng dụng một cách tự động (như một AI vậy, chắc là một AI đấy :D ).  

Đọc thêm: [Improve Application Startup Speed With Preload in Ubuntu](https://itsfoss.com/improve-application-startup-speed-with-preload-in-ubuntu/)

<p class="last-modified-date" style="text-align: right; font-size: 11px; color: #ADADAD;"></p>
