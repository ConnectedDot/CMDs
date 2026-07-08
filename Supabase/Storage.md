# Supabase Storage

## Use Cases

- User avatars
- Health report uploads
- Device data exports
- Family documents
- Music or media assets if required

## RLS

Storage policies should restrict objects by user ownership.

Typical object path style:

```text
user-id/file-name.ext
```

## Buckets

Example buckets:

```text
avatars
health-reports
device-exports
```

## Notes

Storage access should be designed together with database RLS.
