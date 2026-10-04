# English Edge — Admin Dashboard (separate repo, static, no build step)

Uses the SAME Supabase project as the main site (schema lives in the main repo: `supabase/schema.sql`).

1. Edit `config.js` (same URL + anon key as the main site).
2. Create your admin account by signing up on the main site (verify email), then run in SQL Editor:
   `insert into public.admins (user_id) select id from auth.users where email = 'YOUR-EMAIL';`
3. Add the admin URL to Supabase → Authentication → Redirect URLs.
4. Push to GitHub → import as a second Vercel project.
Admin rights are enforced by RLS + security-definer functions, not by the UI.
