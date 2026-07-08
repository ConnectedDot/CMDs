# Supabase Row Level Security

## Purpose

RLS protects database rows so users only access permitted data.

## Common Pattern

Enable RLS:

```sql
alter table public.profiles enable row level security;
```

Allow users to read own profile:

```sql
create policy "Users can read own profile"
on public.profiles
for select
using (auth.uid() = id);
```

## Service Role

Service-role bypasses RLS and must never be used in client apps.

## HealthPulse Notes

For HealthPulse, most user-owned tables should include:

```sql
user_id uuid references auth.users(id)
```

Then RLS can use:

```sql
auth.uid() = user_id
```
