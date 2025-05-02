# Windows CMD and PowerShell Commands Organized by Usage

## 1. **File and Directory Management**
- `dir` - Lists files and directories in the current directory.
- `cd` - Changes the current directory.
- `mkdir` - Creates a new directory.
- `rmdir` - Removes a directory.
- `del` - Deletes one or more files.
- `copy` - Copies files from one location to another.
- `move` - Moves files or renames them.
- `ren` - Renames a file or directory.
- `attrib` - Displays or changes file attributes.
- `tree` - Displays a graphical directory structure.
- `pushd` - Saves the current directory and changes to a new one.
- `popd` - Restores the previous directory saved by `pushd`.

## 2. **Storage Utilities**
- `diskpart` - Opens the Disk Partition utility.
- `chkdsk` - Checks a disk for errors and repairs them.
- `format` - Formats a disk for use.
- `vol` - Displays the volume label and serial number of a disk.
- `fsutil` - Performs advanced file system tasks.
- `mountvol` - Manages volume mount points.
- `defrag` - Defragments a disk to improve performance.
- `diskperf` - Configures disk performance counters.

## 3. **Networking**
- `ping` - Tests connectivity to a network host.
- `ipconfig` - Displays network configuration.
- `netstat` - Displays network connections and statistics.
- `tracert` - Traces the route packets take to a host.
- `nslookup` - Queries DNS servers for information.
- `net` - Manages network resources (e.g., `net use`, `net share`).
- `arp` - Displays or modifies the ARP table.
- `route` - Displays or modifies the routing table.
- `telnet` - Connects to a remote host using the Telnet protocol.
- `ftp` - Transfers files to/from a remote server.
- `curl` - Transfers data from or to a server (PowerShell).
- `wget` - Downloads files from the web (PowerShell).

## 4. **System Information and Diagnostics**
- `systeminfo` - Displays detailed system information.
- `tasklist` - Lists running processes.
- `taskkill` - Terminates a running process.
- `sfc` - Scans and repairs system files.
- `wmic` - Displays system management information.
- `msinfo32` - Opens the System Information tool.
- `dxdiag` - Opens the DirectX Diagnostic Tool.
- `driverquery` - Displays a list of installed drivers.
- `eventvwr` - Opens the Event Viewer.
- `perfmon` - Opens the Performance Monitor.

## 5. **User and Permissions Management**
- `net user` - Manages user accounts.
- `whoami` - Displays the current user.
- `runas` - Runs a program as another user.
- `icacls` - Displays or modifies file permissions.
- `net localgroup` - Manages local user groups.
- `logoff` - Logs off the current user.
- `passwd` - Changes the user password (PowerShell).

## 6. **Power Management**
- `shutdown` - Shuts down or restarts the computer.
- `powercfg` - Configures power settings.
- `sleep` - Puts the computer to sleep (PowerShell).
- `hibernate` - Puts the computer into hibernation (PowerShell).
- `wake` - Configures wake timers (PowerShell).

## 7. **Scripting and Automation**
- `for` - Loops through a set of commands.
- `if` - Performs conditional processing.
- `echo` - Displays messages or turns command echoing on/off.
- `set` - Sets or displays environment variables.
- `call` - Calls a batch file from another batch file.
- `pause` - Pauses the execution of a script.
- `goto` - Directs the command interpreter to a labeled line in a script.
- `start` - Starts a separate window to run a program or command.
- `exit` - Exits the command prompt or script.

## 8. **Compression and Archiving**
- `compact` - Displays or alters file compression.
- `tar` - Archives files (PowerShell).
- `zip` - Compresses files (PowerShell).
- `unzip` - Extracts files from a ZIP archive (PowerShell).
- `7z` - Compresses or extracts files using 7-Zip (if installed).

## 9. **Security and Encryption**
- `cipher` - Encrypts or decrypts files and directories.
- `certutil` - Manages certificates and keys.
- `secedit` - Configures security policies.
- `gpupdate` - Updates Group Policy settings.
- `gpresult` - Displays Group Policy results for a user or computer.
- `schtasks` - Schedules tasks to run automatically.

## 10. **Azure-Specific Commands**
- `az login` - Logs into Azure CLI.
- `az storage` - Manages Azure storage accounts.
- `az vm` - Manages Azure virtual machines.
- `az network` - Manages Azure networking resources.
- `az group` - Manages Azure resource groups.
- `az account` - Manages Azure subscriptions.
- `az monitor` - Manages Azure monitoring and alerts.
- `az keyvault` - Manages Azure Key Vault resources.

## 11. **Miscellaneous**
- `cls` - Clears the screen.
- `help` - Displays help for commands.
- `time` - Displays or sets the system time.
- `date` - Displays or sets the system date.
- `exit` - Exits the command prompt or script.
- `title` - Sets the title of the command prompt window.
- `color` - Changes the text and background colors of the command prompt.
- `ver` - Displays the Windows version.
- `echo.` - Outputs a blank line in the command prompt.

