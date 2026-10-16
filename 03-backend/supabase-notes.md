Features:

- Auth via frontend SDK (`supabase.auth.signUp()`)
- Authorization via RLS policies (`USING` for reads, `WITH CHECK` for writes)
- Realtime subscriptions
- Storage (private buckets + RLS on `storage.objects`)
- Edge functions (Deno)
- Cron jobs (`pg_cron`)

## Free-tier limits

| Feature | Limit |
| --- | --- |
| Database | 500 MB |
| API requests | Unlimited (fair-use; egress/compute bound) |
| Auth MAUs | 50k |
| File storage | 1 GB |
| Egress | 5 GB |
| Serverless functions | 500K invocations/mo |
| Realtime | 200 concurrent connections |
| Projects | 2 active |
| Inactivity pause | ⚠️ After 7 days (free tier only) |

No branching / point-in-time recovery on free tier — that's what pushes teams to Pro.
