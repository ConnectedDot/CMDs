# PowerShell Guide

## Check Execution Policy

```powershell
Get-ExecutionPolicy -List
```

## Allow Local Scripts for Current User

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

## Check Whether PowerShell Is Elevated

```powershell
whoami /groups | findstr S-1-5-32-544
```

If this returns administrator group information, the session may be elevated.

## Common Issue: Running from System32

If your prompt starts at:

```text
PS C:\WINDOWS\system32>
```

you may be in an elevated/admin context.

For normal development, move to your project folder:

```powershell
cd "$HOME\Downloads"
```

or:

```powershell
cd "$HOME\Desktop"
```

## Useful Commands

```powershell
Get-Command node
Get-Command bun
Get-Command git
Get-Command supabase
where.exe node
where.exe bun
where.exe git
where.exe supabase
```
