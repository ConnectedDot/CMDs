# Supabase Database Migrations

## Purpose

Use migrations to track database schema changes in a repeatable way.

## HealthPulse Migration Engine Commands

```bash
bun install
bun run db:verify
bun run db:dry-run
bun run db:migrate
```

## Connection Notes

Prefer a database connection suitable for migrations.

If direct DB host fails with DNS or IPv6 issues:

```text
getaddrinfo ENOTFOUND db.<project-ref>.supabase.co
```

Use the Supabase Session Pooler connection string from:

```text
Supabase Dashboard → Project Settings → Database → Connection string → Session pooler
```

## Migration Journal

A safe migration engine should track:

- migration name
- checksum
- execution time
- success/failure
- applied timestamp

## Never Commit

```text
SUPABASE_DB_URL
SUPABASE_SERVICE_ROLE_KEY
SUPABASE_ACCESS_TOKEN
```
