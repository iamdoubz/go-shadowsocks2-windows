# go-shadowsocks2-windows
A startup script for windows and [go-shadowsocks2](https://github.com/shadowsocks/go-shadowsocks2)

## Assumptions
1. You have already compiled the binary to a folder C:\Users\user\github\go-shadowsocks2
2. You are tired of manually running the go-shadowsocks2 binary
3. You are running windows because of reasons

## Steps
1. Copy the files `start.bat` and `start.ps1` into the go-shadowsocks2 binary directory (see #Assumptions #1)
2. Create a New Task Scheduler
3. General tab
    - Name: SOCKS5
    - Description: Go-Shadow2 SOCKS5 Proxy
    - Run whether user is logged on or not
    - Do not store password
    - Run with highest privileges
    - Configure for: Windows 10
4. Triggers tab
    - At log on
5. Actions tab
    - Start a program
    - Program/script: `C:\Users\user\github\go-shadowsocks2\start.bat`
    - Start in (optional): `C:\Users\user\github\go-shadowsocks2`
6. Conditions tab
    - Network: Start only if the following network connection is available (select your network name here)
7. Settings tab
    - Allow task to be run on demand
    - Run task as soon as possible after a scheduled start is missed
    - If the task fails, restart every `5 minutes`
    - Attempt to restart up to `6` times
    - If the task is already running, then the following rule applies: `Do not start a new instance`
