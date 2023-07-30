---
layout: post
title: "Sử dụng Total Commander để truy cập vào Linux thông qua giao thức SSH"
date: 2020-02-15 15:15:15 +0700
categories: [linux, windows]
---

#### Yêu cầu
[Total Commander](https://www.ghisler.com/download.htm)  
[SFTP Plugin](https://www.totalcommander.ch/win/fs/sftpplug.zip)  

#### Cài đặt
Mở tệp tin **sftpplug.zip** trong **Total Commander** để cài đặt plugin **SFTP**. Sau khi cài đặt thành công, khởi động lại chương trình **Total Commander**.  

## Thiết lập
Trong chương trình **Total Commander**, nhấn vào biểu tượng **Network Neighborhood**, truy cập vào **Secure FTP**. Nhấn phím **F7** để đặt tên và tạo kết nối mới. Không sử dụng khoảng trắng (space) trong quá trình đặt tên. Sau đó, chương trình **Total Commander** sẽ đưa người dùng tới cửa sổ **Connect to SFTP Server**.

{:refdef: style="text-align: center;"}
![Connect to SFTP Server](/static/img/posts/total-commander/Connect_to_SFTP_Server.png)
{: refdef}  

Tại đây, thiết lập đơn giản với địa chỉ IP, tên đăng nhập và mật khẩu của Linux Server. Sau đó, nhấn **OK** để đóng cửa sổ **Connect to SFTP Server**. Quay trở lại **Secure FTP**, truy cập vào tên của kết nối đã đặt ở bên trên. 

#### Sử dụng
Bằng cách này, có thể sử dụng phần mềm, chương trình trên Windows để mở, chỉnh sửa, các tệp tin trên hệ thống Linux.  

Đọc thêm: [Why doesn't Total Commander support a connection by SSH?](https://www.ghisler.com/efaqftp.htm)  
