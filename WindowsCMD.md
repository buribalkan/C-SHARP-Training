# Windows Command Line (CMD) - Comprehensive Command Reference

This document provides a categorized list of essential and advanced Windows Command Prompt commands with English explanations.

---

## ✩ File and Directory Commands


| Command | Description |
|---------|-------------|
| `dir` | Lists files and folders in the current directory. |
| `cd [folder]` | Changes the current directory. |
| `cd ..` | Moves up one directory level. |
| `md [folder]` / `mkdir [folder]` | Creates a new directory. |
| `rd [folder]` / `rmdir [folder]` | Deletes an empty directory. |
| `del [filename]` | Deletes a file. |
| `copy [source] [destination]` | Copies files. |
| `xcopy [src] [dst] /s /e` | Recursively copies files and directories. |
| `move [src] [dst]` | Moves or renames files. |
| `ren [oldname] [newname]` | Renames a file or directory. |


---

## ✩ System Information & Management


| Command | Description |
|---------|-------------|
| `systeminfo` | Displays system configuration info. |
| `tasklist` | Lists running processes. |
| `taskkill /IM [name] /F` | Force-kills process by name. |
| `hostname` | Shows the computer name. |
| `ipconfig` / `ipconfig /all` | Shows IP/network settings. |
| `ping [host]` | Tests network connection. |
| `tracert [host]` | Shows path to host. |
| `netstat` | Displays open ports and connections. |
| `shutdown /s /t 0` | Shuts down system. |
| `shutdown /r /t 0` | Restarts system. |


---

## ✩ Disk and File System Tools


| Command | Description |
|---------|-------------|
| `chkdsk` | Checks disk for errors. |
| `chkdsk C: /f` | Fixes disk errors on C:. |
| `diskpart` | Launches partition tool. |
| `format [drive:]` | Formats a drive. |
| `sfc /scannow` | Scans & repairs system files. |
| `defrag [drive:]` | Defragments disk. |


---

## ✩ User & Permissions Commands


| Command | Description |
|---------|-------------|
| `net user` | Lists user accounts. |
| `net user [user] [pass] /add` | Adds a new user. |
| `net user [user] /delete` | Deletes a user. |
| `net localgroup administrators [user] /add` | Adds user to admin group. |


---

## ✩ Pipe `|` Usage


| Example | Description |
|---------|-------------|
| `dir | more` | Paginates directory listing. |
| `tasklist | find "chrome"` | Filters running tasks. |
| `ipconfig | find "IPv4"` | Filters IP output. |
| `systeminfo | findstr "OS"` | Filters OS info. |


---

## ✩ Task Management Commands


| Command | Description |
|---------|-------------|
| `tasklist` | Lists all tasks. |
| `tasklist /fi "imagename eq name.exe"` | Filters tasks by name. |
| `taskkill /IM [name]` | Kills tasks by name. |
| `taskkill /PID [id]` | Kills by PID. |
| `taskkill /F /IM [name]` | Force kill by name. |


---

## ✩ Advanced Process & Service Commands


| Command | Description |
|---------|-------------|
| `wmic process list brief` | Brief process list. |
| `wmic process where "name='x.exe'" delete` | Kill process by WMI. |
| `wmic service list brief` | Shows services. |
| `wmic os get caption,version` | Shows OS info. |
| `net start` / `net stop [svc]` | Starts/stops a service. |
| `net session` | Active user sessions. |
| `sc query` / `sc start` / `sc stop` | Service management. |


---

## ✩ Network Utilities


| Command | Description |
|---------|-------------|
| `ipconfig /release` / `/renew` | Releases/renews IP. |
| `ipconfig /flushdns` | Flushes DNS cache. |
| `nslookup [domain]` | DNS lookup. |
| `netstat -an` | Lists ports. |
| `netsh wlan show profiles` | Shows saved Wi-Fi profiles. |
| `netsh wlan show profile name="SSID" key=clear` | Reveals Wi-Fi password. |
| `tracert [host]` | Shows route to host. |


---

## ✩ Disk & File Tools (Advanced)


| Command | Description |
|---------|-------------|
| `tree` | Displays directory structure. |
| `attrib` | Shows/sets file attributes. |
| `cipher /w:C:\` | Wipes free space. |
| `fsutil file createnew test.txt 1000000` | Creates dummy file. |
| `robocopy [src] [dst] /MIR` | Mirrors folders. |
| `compact /c /s` | Compresses files. |


---

## ✩ Scheduled Tasks


| Command | Description |
|---------|-------------|
| `schtasks /query /fo LIST /v` | Lists scheduled tasks. |
| `schtasks /create /tn "task" /tr "notepad.exe" /sc daily /st 10:00` | Creates daily task. |
| `schtasks /delete /tn "task"` | Deletes a task. |


---

## ✩ Security & Encryption


| Command | Description |
|---------|-------------|
| `cipher /e [file]` | Encrypts a file. |
| `cipher /d [file]` | Decrypts a file. |
| `net accounts` | Password policies. |
| `net accounts /minpwlen:10` | Sets minimum password length. |
| `secedit` | Security audit tool. |


---

## ✩ Automation & Scripting


| Command | Description |
|---------|-------------|
| `for /f "tokens=*" %i in (file.txt) do echo %i` | Loops over file lines. |
| `if exist "file.txt" del file.txt` | Deletes file if it exists. |
| `set var=value` | Defines a variable. |
| `call script.bat` | Calls another script. |


---

## ✩ Fun / Cosmetic


| Command | Description |
|---------|-------------|
| `title Hacker Mode` | Sets CMD window title. |
| `color a` | Sets green text color. |
| `prompt $t $d $g` | Customizes CMD prompt. |
| `echo ^G` | Emits a beep sound. |


---

## ✩ GUI Shortcuts from CMD


| Command | Description |
|---------|-------------|
| `resmon` | Opens Resource Monitor. |
| `perfmon` | Opens Performance Monitor. |
| `taskmgr` | Opens Task Manager. |
| `msinfo32` | Opens System Info. |
| `control` | Opens Control Panel. |
| `appwiz.cpl` | Opens Programs and Features. |
| `sysdm.cpl` | Opens System Properties. |
| `main.cpl` | Opens Mouse settings. |
| `inetcpl.cpl` | Opens Internet Options. |
| `ncpa.cpl` | Opens Network Connections. |

## ✩ Environment Variables


| Command | Description |
|---------|-------------|
| `set` | Lists all environment variables. |
| `set [var]=[value]` | Temporarily sets a variable. |
| `echo %USERNAME%` | Displays current username. |
| `echo %COMPUTERNAME%` | Displays computer name. |
| `echo %PATH%` | Displays PATH variable. |
| `setx [var] [value]` | Sets a permanent environment variable. |


---

For scripting, troubleshooting, or automation, CMD remains a powerful tool when used with precision. For even more capabilities, consider exploring PowerShell.

---


