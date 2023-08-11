---
layout: post
title: "Điều khiển từ xa bằng tiện ích mở rộng Remote - Tunnels của Visual Studio Code"
date: 2023-08-07 14:32:01 +0700
categories: [linux, ubuntu, windows]
---

Phần mềm Visual Studio Code của Microsoft phát hành một tiện ích mở rộng (extension) có tên là [Remote - Tunnels](https://marketplace.visualstudio.com/items?itemName=ms-vscode.remote-server).

{:refdef: style="text-align: center;"}
![Remote - Tunnels](/static/img/Remote_Tunnels/Remote_Tunnels.png)
{: refdef}

Tiện ích mở rộng **Remote - Tunnels** cho phép người dùng kết nối tới một máy tính từ xa, chẳng hạn như máy tính để bàn hoặc máy ảo (VM), máy chủ Ubuntu (Linux) thông qua một đường hầm (tunnel) an toàn. Sau đó, người dùng có thể kết nối an toàn tới máy tính đó từ mọi nơi mà không cần SSH.

{:refdef: style="text-align: center;"}
![SSH Tunnel](/static/img/Remote_Tunnels/SSH_Tunnel.png)
{: refdef}

Trên máy chủ cần kết nối đến, sử dụng tính năng **Turn on Remote Tunnel Access...** có sẵn trên Visual Studio Code hoặc cài đặt [Code CLI](https://code.visualstudio.com/#alt-downloads) để sử dụng riêng biệt mà không cần cài đặt Visual Studio Code.

{:refdef: style="text-align: center;"}
![Turn on Remote Tunnel Access...](/static/img/Remote_Tunnels/Turn_on_Remote_Tunnel_Access.png)
{: refdef}

{:refdef: style="text-align: center;"}
![Code CLI](/static/img/Remote_Tunnels/Code_CLI.png)
{: refdef}

Trên hệ điều hành Ubuntu/Linux Mint, tải về và giải nén **Code CLI** bằng câu lệnh:
```bash
curl -Lk 'https://code.visualstudio.com/sha/download?build=stable&os=cli-alpine-x64' --output vscode_cli.tar.gz

tar -xf vscode_cli.tar.gz
```

Tạo một đường hầm (tunnel) an toàn bằng lệnh:
```bash
code tunnel
# Hoặc
./code tunnel
```
Làm theo yêu cầu trên cửa sổ Terminal: chấp nhận **Do you accept the terms in the License Agreement**, mở đường dẫn (link) [github.com](https://github.com/) mà **Code CLI** cung cấp bằng trình duyệt, nhập mã, chấp nhận **Authorize Visual-Studio-Code**, đặt tên cho máy chủ.

Cửa sổ Terminal của **Code CLI** sẽ cho ra một đường dẫn (link) có dạng `https://vscode.dev/tunnel/<machine_name>/<folder_name>`, người dùng sử dụng đường dẫn này để điều khiển (remote) ở máy khách.

Trên Visual Studio Code của máy khách, cài đặt tiện ích mở rộng (extension) [Remote - Tunnels](https://marketplace.visualstudio.com/items?itemName=ms-vscode.remote-server). Sử dụng tiện ích này từ thực đơn (menu) **View** > **Command Palette...** > **Remote-Tunnels: Connect to Tunnel...**. Nhập vào đường dẫn (link) ở bên trên, nhấn phím **Enter** và làm theo yêu cầu của Visual Studio Code.

Kết nối thành công thì tên của đường hầm (tunnel) sẽ có trong thực đơn (menu) **Remote Explorer** của Visual Studio Code.

**Đọc thêm**:
- [Developing with Remote Tunnels](https://code.visualstudio.com/docs/remote/tunnels)
