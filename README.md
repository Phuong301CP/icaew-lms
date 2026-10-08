# ICAEW LMS

Static PWA frontend hosted on GitHub Pages with Supabase providing authentication, database, storage and cloud sync.

## Architecture

- GitHub repository: source of truth and version history
- GitHub Actions + Pages: static frontend deployment
- Supabase Auth: two-user authentication
- Supabase Postgres: subjects, chapters, exercises, lessons, questions, user progress and preferences
- Supabase Storage: private source files for AI import
- Supabase Edge Function: AI import processing

## Main routes

- `/` — Quiz LMS
- `/admin.html` — Admin CMS
- `/lessons.html` — Theory/Lessons reader

## Deploy

1. Create a GitHub repository named `icaew-lms`.
2. Push the contents of this repository to `main`.
3. In GitHub repository settings, enable **Pages → Source: GitHub Actions**.
4. The workflow `.github/workflows/pages.yml` deploys automatically on every push to `main`.
5. Update Supabase Auth URL configuration to the final GitHub Pages URL before using email confirmation on the new domain.

## Security

- Supabase publishable key is intentionally public and protected by RLS.
- Never commit a Supabase service-role key or an OpenAI API key.
- AI provider keys belong only in Supabase Edge Function secrets.
- Current LMS access is limited by RLS to the two allowlisted accounts.

## AI Import

The frontend calls:

`https://uangiwgznukuicrfnohq.supabase.co/functions/v1/icaew-ai-import`

The function should read private files from bucket `content-imports`, extract structured questions/lessons, and return JSON for human review before publishing.

## Migration status

- [x] Core quiz source migrated from V7.5
- [x] Lower-friction quiz flow added
- [x] Supabase cloud sync preserved
- [x] Database-driven Subject → Chapter → Exercise → Question loading
- [x] Admin CMS built
- [x] Lessons reader built
- [x] PWA manifest + service worker
- [x] GitHub Pages deployment workflow
- [ ] Create GitHub repository
- [ ] Push repo contents
- [ ] Enable GitHub Pages
- [ ] Point Supabase Auth redirect URLs to GitHub Pages domain
- [ ] Finalize/deploy AI Import Edge Function and provider secret
- [ ] Cross-device production test
- [ ] Retire Floot after successful migration