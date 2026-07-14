# Kano Food-Watch

Kano Food‑Watch is a community-driven web app to report and browse food safety incidents in Kano, Nigeria.

Features
- Report incidents (title, description, photo, geolocation)
- Browse recent reports with map view
- Supabase-powered Auth, Postgres, and Storage (scaffold)
- i18n support (English + Hausa scaffolded)

Stack
- Next.js + TypeScript
- Tailwind CSS
- Supabase (Auth, Postgres, Storage)
- React-Leaflet for maps

Quick start
1. Create a Supabase project and create a table named `reports` (see SQL in repo).
2. Copy `.env.local.example` to `.env.local` and fill values.
3. Install dependencies:

   npm install

4. Run locally:

   npm run dev

Supabase table example

Run this SQL in your Supabase SQL editor to create the `reports` table:

```sql
create extension if not exists pgcrypto;

CREATE TABLE public.reports (
  id uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  title text,
  description text,
  latitude numeric,
  longitude numeric,
  image_url text,
  user_id uuid,
  created_at timestamptz DEFAULT now()
);
```

Notes
- This scaffold includes a TODO for image upload to Supabase Storage. You can enable it by adding SUPABASE keys in `.env.local`.
- Hausa translations are available in `src/i18n/ha.json`.

License
MIT — see LICENSE file.
