# WSL Guide

## Purpose

WSL can be used as an alternative when Windows blocks tooling or when Linux-compatible CLI behavior is preferred.

## Install WSL

```powershell
wsl --install
```

Restart your machine if prompted.

## Check WSL

```powershell
wsl --status
wsl -l -v
```

## When to Use WSL

- Windows blocks executable shims.
- Native Windows CLI has path or permission issues.
- Project tooling behaves better in Linux.
- You need Linux shell scripts.

## Notes

For mobile development with Expo, Windows-native tooling may still be easier because device networking and emulators are often configured on Windows.
