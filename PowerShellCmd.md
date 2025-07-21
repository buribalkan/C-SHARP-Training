# Windows PowerShell - Comprehensive Command Reference

This guide provides categorized PowerShell commands with clear explanations, similar to the CMD and macOS Terminal references.

---

## ✩ File and Directory Management


| Command | Description |
|---------|-------------|
| `Get-ChildItem` / `ls` | Lists files and folders. |
| `Set-Location` / `cd` | Changes current directory. |
| `New-Item -ItemType Directory -Name "Folder"` | Creates a new folder. |
| `Remove-Item -Path "file.txt"` | Deletes a file. |
| `Copy-Item -Path file.txt -Destination backup.txt` | Copies files. |
| `Move-Item -Path a.txt -Destination b.txt` | Moves or renames files. |
| `Rename-Item -Path file.txt -NewName new.txt` | Renames a file. |


---

## ✩ System Information & Diagnostics


| Command | Description |
|---------|-------------|
| `Get-ComputerInfo` | Displays detailed system info. |
| `Get-Process` | Lists running processes. |
| `Stop-Process -Name notepad` | Kills process by name. |
| `Get-Service` | Lists all services. |
| `Start-Service "Name"` / `Stop-Service "Name"` | Starts/stops a service. |
| `Restart-Computer` | Restarts the machine. |
| `Get-EventLog -LogName System -Newest 20` | Shows recent system logs. |


---

## ✩ Network & Internet Tools


| Command | Description |
|---------|-------------|
| `Test-Connection google.com` | Pings a host. |
| `Get-NetIPConfiguration` | Shows network config. |
| `Resolve-DnsName openai.com` | DNS lookup. |
| `Get-NetTCPConnection` | Displays TCP connections. |
| `ipconfig /all` | Still works for compatibility. |


---

## ✩ User & Account Management


| Command | Description |
|---------|-------------|
| `Get-LocalUser` | Lists local users. |
| `New-LocalUser -Name "User" -Password (Read-Host -AsSecureString)` | Creates a user. |
| `Remove-LocalUser -Name "User"` | Deletes a local user. |
| `Add-LocalGroupMember -Group "Administrators" -Member "User"` | Adds user to admin group. |


---

## ✩ Environment Variables


| Command | Description |
|---------|-------------|
| `$env:PATH` | Displays PATH variable. |
| `$env:USERNAME` | Shows current username. |
| `[Environment]::SetEnvironmentVariable("VAR", "Value", "User")` | Sets user-level env variable. |
| `Get-ChildItem Env:` | Lists all env variables. |


---

## ✩ Task Scheduler


| Command | Description |
|---------|-------------|
| `Get-ScheduledTask` | Lists scheduled tasks. |
| `Register-ScheduledTask` | Creates new task (complex). |
| `Unregister-ScheduledTask -TaskName "MyTask"` | Deletes a task. |


---

## ✩ Disk and Filesystem Tools


| Command | Description |
|---------|-------------|
| `Get-PSDrive` | Shows drive info. |
| `Get-Volume` | Lists volumes. |
| `Get-Disk` | Lists physical disks. |
| `Clear-RecycleBin` | Empties recycle bin. |
| `Check-Disk` (via `chkdsk`) | Use CMD: `chkdsk C:` |


---

## ✩ Software & Package Management


| Command | Description |
|---------|-------------|
| `Get-Package` | Lists installed packages. |
| `Install-Package -Name "git"` | Installs a package (via provider). |
| `Uninstall-Package -Name "git"` | Uninstalls a package. |
| `winget install vscode` | Installs via winget. |


---

## ✩ Scripting & Automation


| Command | Description |
|---------|-------------|
| `foreach ($file in Get-ChildItem)` | Loop over files. |
| `if (Test-Path file.txt) { Remove-Item file.txt }` | Conditional file removal. |
| `$var = "value"` | Variable assignment. |
| `.\script.ps1` | Runs a script file. |


---

## ✩ GUI & Control Panel Access


| Command | Description |
|---------|-------------|
| `Start-Process taskmgr` | Opens Task Manager. |
| `Start-Process msinfo32` | Opens System Info. |
| `Start-Process control` | Opens Control Panel. |
| `Start-Process appwiz.cpl` | Programs and Features. |
| `Start-Process ncpa.cpl` | Network Connections. |


---

PowerShell is a robust scripting environment with .NET integration, ideal for advanced automation, configuration, and cross-platform scripting.

---


