---
layout: post
title: "Thêm Git Bash vào Windows Terminal"
date: 2016-04-19 20:15:33 +0700
categories: [Information Technology]
tags: [git]
img_path: /assets/img/GitBashWindowsTerminal/
---

![Git Bash](2019-11-26_14-59-51.png)
_Git Bash_

Đảm bảo đã cài đặt [git-scm](https://git-scm.com/downloads) trước đã.

Tải về [Windows Terminal](https://github.com/microsoft/terminal).

Sau đó mở cài đặt của Windows Terminal như hình dưới đây:

![Setting of Windows Terminal](2019-11-26_14-55-40.png)
_Setting of Windows Terminal_

Thêm đoạn mã sau vào phần `profiles` của Windows Terminal:
```json
"profiles" :
[
    {
        "guid": "{00000000-0000-0000-0000-000000000001}",
        "acrylicOpacity" : 0.75,
        "closeOnExit" : true,
        "colorScheme" : "GitBash",
        "commandline" : "\"%PROGRAMFILES%\\Git\\usr\\bin\\bash.exe\" --login -i -l",
        "cursorColor" : "#FFFFFF",
        "cursorShape" : "bar",
        "fontFace" : "Consolas",
        "fontSize" : 10,
        "historySize" : 9001,
        "icon" : "%PROGRAMFILES%\\Git\\mingw64\\share\\git\\git-for-windows.ico",
        "name" : "GitBash",
        "padding" : "0, 0, 0, 0",
        "snapOnInput" : true,
        "startingDirectory" : "%USERPROFILE%",
        "useAcrylic" : false
    },
]
```

Thêm tiếp đoạn mã này vào phần `schemes`:
```json
"schemes" :
[
    {
        "background" : "#000000",
        "black" : "#0C0C0C",
        "blue" : "#6060ff",
        "brightBlack" : "#767676",
        "brightBlue" : "#3B78FF",
        "brightCyan" : "#61D6D6",
        "brightGreen" : "#16C60C",
        "brightPurple" : "#B4009E",
        "brightRed" : "#E74856",
        "brightWhite" : "#F2F2F2",
        "brightYellow" : "#F9F1A5",
        "cyan" : "#3A96DD",
        "foreground" : "#bfbfbf",
        "green" : "#00a400",
        "name" : "GitBash",
        "purple" : "#bf00bf",
        "red" : "#bf0000",
        "white" : "#ffffff",
        "yellow" : "#bfbf00",
        "grey" : "#bfbfbf"
    },
]
```

> Muốn đặt Git Bash là chương trình mặc định mỗi khi khởi động Windows Terminal thì có thể thay đổi giá trị `defaultProfile` trong phần `globals` theo `guid` của Git Bash.
{:.prompt-info}
