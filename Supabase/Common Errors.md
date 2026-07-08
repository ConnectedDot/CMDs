# Supabase Common Errors

## EPERM with npx Supabase

```text
spawnSync ... supabase.exe EPERM
```

Likely cause:

- Windows Security blocked executable
- corporate endpoint protection
- permission policy

Fix:

- install via Scoop or Winget
- check Windows Security Protection history
- ask IT to whitelist

## DNS Error

```text
getaddrinfo ENOTFOUND db.<project-ref>.supabase.co
```

Fix:

- check internet/DNS
- try Supabase Session Pooler
- verify project ref
- check VPN/corporate firewall

## Service Role Warning

If a service-role key was pasted into chat, terminal screenshots, or Git history, rotate it immediately.
