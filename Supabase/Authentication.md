# Supabase Authentication

## Client Keys

Mobile apps should use:

```text
SUPABASE_URL
SUPABASE_ANON_KEY
```

Never use:

```text
SUPABASE_SERVICE_ROLE_KEY
```

inside Expo or React Native.

## Common Screens

- Login
- Signup
- Forgot password
- Password reset
- Profile onboarding

## Session Handling

Use a central auth provider and wrap the root app layout.

Example concept:

```tsx
<AuthProvider>
  <Slot />
</AuthProvider>
```
