# Supabase CLI Guide

## Login

```bash
supabase login
```

## Link Project

```bash
supabase link --project-ref <project-ref>
```

## Check Status

```bash
supabase status
```

## Deploy Edge Function

```bash
supabase functions deploy <function-name>
```

## Set Secrets

```bash
supabase secrets set MY_SECRET=value
```

or:

```bash
supabase secrets set --env-file ./supabase/functions/.env.production
```

## Common Windows Issue

If `supabase` shim fails, run the binary directly:

```powershell
& "$HOME\scoop\apps\supabase\current\supabase.exe" login
```
