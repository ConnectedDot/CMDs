# Supabase Installation Guide

## Install Options

Recommended Windows options:

```powershell
scoop install supabase
```

or:

```powershell
winget install Supabase.CLI
```

Avoid relying only on:

```bash
npx supabase
```

on managed Windows machines because the downloaded executable may be blocked.

## Verify

```bash
supabase --version
```

## Direct Executable Test

```powershell
& "$HOME\scoop\apps\supabase\current\supabase.exe" --version
```

## Login

```bash
supabase login
```

## Link Project

```bash
supabase link --project-ref <project-ref>
```
