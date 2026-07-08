# Windows PATH Guide

## Purpose

This guide explains how to inspect and repair the Windows `PATH` variable when developer tools fail to run.

Common symptoms:

```text
command not found
Get-Command : The term 'robocopy' is not recognized
PowerShell does not load commands from the current location
```

## Required Core Windows Paths

These should normally exist in PATH:

```text
C:\Windows
C:\Windows\System32
C:\Windows\System32\WindowsPowerShell\v1.0
```

## Check Current PATH

```powershell
$env:Path
```

## Check a Command

```powershell
Get-Command robocopy
where.exe robocopy
```

## Temporary PATH Fix

This only fixes the current PowerShell session:

```powershell
$env:Path = "C:\Windows\System32;C:\Windows;C:\Windows\System32\WindowsPowerShell\v1.0;" + $env:Path
```

Verify:

```powershell
Get-Command robocopy
```

## Permanent User PATH Fix

```powershell
[Environment]::SetEnvironmentVariable(
  "Path",
  "C:\Windows\System32;C:\Windows;C:\Windows\System32\WindowsPowerShell\v1.0;" + [Environment]::GetEnvironmentVariable("Path", "User"),
  "User"
)
```

Close and reopen PowerShell after updating PATH.

## Python PATH

Check Python:

```powershell
python --version
py --version
where.exe python
where.exe py
```

Common user Python launcher path:

```text
%USERPROFILE%\AppData\Local\Microsoft\WindowsApps
```

## Notes

On managed/business laptops, PATH can be altered by endpoint management software or corporate images.
