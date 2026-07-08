# Supabase Edge Functions

## Purpose

Edge Functions run backend logic close to users and are useful for AI calls, secure service-role operations, and webhooks.

## Structure

```text
supabase/
└── functions/
    └── health-ai-assistant/
        └── index.ts
```

## Deploy

```bash
supabase login
supabase link --project-ref <project-ref>
supabase functions deploy health-ai-assistant
```

## Secrets

```bash
supabase secrets set AZURE_OPENAI_API_KEY=...
supabase secrets set SUPABASE_SERVICE_ROLE_KEY=...
```

or:

```bash
supabase secrets set --env-file ./supabase/functions/.env.production
```

## Local Serve

```bash
supabase functions serve health-ai-assistant
```

## Notes

Do not expose service-role keys in mobile apps.
Use Edge Functions for privileged operations.
