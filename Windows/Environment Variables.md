# Environment Variables Guide

## User vs System Variables

- **User variables** apply only to the current Windows account.
- **System variables** apply to all users and often require administrator access.

## Open Environment Variable UI

```powershell
rundll32 sysdm.cpl,EditEnvironmentVariables
```

## PowerShell Session Variable

```powershell
$env:MY_VARIABLE="value"
```

This lasts only for the current terminal session.

## Permanent User Variable

```powershell
[Environment]::SetEnvironmentVariable("MY_VARIABLE", "value", "User")
```

## Read Variable

```powershell
$env:MY_VARIABLE
```

## Notes for Secrets

Do not commit secrets to Git:

```text
SUPABASE_SERVICE_ROLE_KEY
SUPABASE_ACCESS_TOKEN
DATABASE_URL
AZURE_OPENAI_API_KEY
```

Use `.env` locally and secret stores in deployment.
