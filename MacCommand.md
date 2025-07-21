# macOS Terminal - Comprehensive Command Reference

This guide provides categorized and practical macOS Terminal commands with English explanations, similar in style to the Windows CMD reference.

---

## ✩ File and Directory Commands


| Command | Description |
|---------|-------------|
| `ls` | Lists files and directories. |
| `ls -la` | Lists all files including hidden with details. |
| `cd [folder]` | Changes current directory. |
| `cd ..` | Moves up one directory level. |
| `mkdir [folder]` | Creates a new directory. |
| `rmdir [folder]` | Removes an empty directory. |
| `rm [file]` | Deletes a file. |
| `rm -r [folder]` | Deletes a folder recursively. |
| `cp [src] [dst]` | Copies files. |
| `cp -R [src] [dst]` | Copies directories recursively. |
| `mv [src] [dst]` | Moves or renames files/folders. |


---

## ✩ System Information & Management


| Command | Description |
|---------|-------------|
| `top` | Displays running processes and system usage. |
| `ps aux` | Lists all processes. |
| `kill [PID]` | Terminates a process by PID. |
| `uptime` | Shows system uptime. |
| `df -h` | Shows disk space in human-readable format. |
| `du -sh *` | Shows folder sizes. |
| `hostname` | Displays the hostname. |
| `whoami` | Prints the current username. |


---

## ✩ Network Tools


| Command | Description |
|---------|-------------|
| `ifconfig` | Shows network interfaces (like `ipconfig`). |
| `ping [host]` | Pings a host. |
| `traceroute [host]` | Traces route to host. |
| `netstat -an` | Displays ports and connections. |
| `lsof -i :[port]` | Lists processes using a port. |
| `dig [domain]` | DNS lookup. |
| `networksetup -listallhardwareports` | Lists all interfaces. |


---

## ✩ Disk and File System Tools


| Command | Description |
|---------|-------------|
| `diskutil list` | Lists all disks and partitions. |
| `diskutil info [disk]` | Shows info about a disk. |
| `fsck` | File system consistency check. |
| `hdiutil create` | Creates a disk image. |
| `hdiutil mount` | Mounts a disk image. |
| `hdiutil detach` | Unmounts a disk image. |


---

## ✩ User Management


| Command | Description |
|---------|-------------|
| `dscl . list /Users` | Lists all users. |
| `id [username]` | Shows user ID and groups. |
| `sudo su - [user]` | Switches to another user. |
| `passwd` | Changes password. |


---

## ✩ Environment Variables


| Command | Description |
|---------|-------------|
| `printenv` | Lists all environment variables. |
| `echo $PATH` | Shows the PATH variable. |
| `export VAR=value` | Temporarily sets a variable. |
| `unset VAR` | Unsets a variable. |


---

## ✩ Scheduled Jobs


| Command | Description |
|---------|-------------|
| `crontab -l` | Lists user cron jobs. |
| `crontab -e` | Edits cron jobs. |
| `launchctl list` | Lists launch agents. |
| `launchctl load/unload [plist]` | Loads/unloads daemons. |


---

## ✩ Package Management (Homebrew)


| Command | Description |
|---------|-------------|
| `brew install [pkg]` | Installs a package. |
| `brew uninstall [pkg]` | Uninstalls a package. |
| `brew list` | Lists installed packages. |
| `brew update` | Updates Homebrew. |
| `brew upgrade` | Upgrades all packages. |


---

## ✩ Fun & Cosmetic


| Command | Description |
|---------|-------------|
| `say "Hello world"` | Speaks text aloud. |
| `cowsay Hello` | ASCII cow with message (requires install). |
| `banner "Text"` | Prints large ASCII text. |


---

## ✩ Useful GUI Shortcuts


| Command | Description |
|---------|-------------|
| `open .` | Opens current folder in Finder. |
| `open -a "App Name"` | Opens an app (e.g., Safari, Notes). |
| `open [file]` | Opens file with default app. |
| `open /System/Applications/Utilities` | Opens Utilities folder. |


---

For more scripting capabilities, macOS users may explore `zsh`, `bash`, or `fish` shells.

---

