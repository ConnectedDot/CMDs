# Windows Security Blockers

## Purpose

Documents common Windows Security and corporate endpoint protection issues that block developer tooling.

## Symptoms

```text
EPERM
spawnSync ... supabase.exe EPERM
Action blocked
Your administrator caused Windows Security to block this action
Shim: Could not create process
```

## Common Causes

- Windows Defender or corporate endpoint protection blocked an executable.
- Downloaded CLI binaries are quarantined.
- Device policy prevents unapproved binaries.
- PowerShell was opened as Administrator when a tool expects a normal user session.

## Checks

Open:

```text
Windows Security → Protection history
```

Look for blocked actions related to:

```text
supabase.exe
node.exe
bun.exe
python.exe
```

## Fix Options

- Restore or allow the executable in Windows Security.
- Ask IT to whitelist the binary.
- Use a personal machine if company policy blocks unsigned or unknown binaries.
- Try installing through approved tools like Winget.
- Avoid running installers as Administrator unless the installer specifically requires it.

## Lesson Learned

If an installer succeeds but the executable cannot launch, check security history before reinstalling repeatedly.
