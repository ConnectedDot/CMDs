# Scoop Guide

## Purpose

Scoop is a Windows package manager useful for installing developer CLIs.

## Install Scoop

Use a normal non-admin PowerShell window:

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
iwr -useb get.scoop.sh | iex
```

## Important

Scoop normally refuses to install from an Administrator PowerShell session.

Error:

```text
Running the installer as administrator is disabled by default.
Abort.
```

Fix:

- Close the elevated PowerShell.
- Open normal PowerShell.
- Run the installer again.

## Supabase CLI

```powershell
scoop bucket add supabase https://github.com/supabase/scoop-bucket.git
scoop install supabase
supabase --version
```

## Repair

```powershell
scoop reset supabase
scoop update supabase
```

## If Shim Fails

Try the executable directly:

```powershell
& "$HOME\scoop\apps\supabase\current\supabase.exe" --version
```

If direct execution fails, Windows Security or corporate endpoint protection may be blocking it.
