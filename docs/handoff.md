# ICAEW LMS handoff status

Repository: `Phuong301CP/icaew-lms`

Production URL: `https://phuong301cp.github.io/icaew-lms/`

## Completed

- GitHub repository created and writable
- GitHub Pages enabled
- automatic deployment from `main`
- Supabase Auth redirected to GitHub Pages
- core quiz and cloud sync migrated
- 52 original Chapter 1 questions migrated to Supabase
- database marked authoritative for migrated exercises
- Admin CMS active
- Lessons reader active
- Gemini AI Import active
- AI source-context mismatch protection active
- content audit history active
- content snapshots/backups active
- non-destructive hide/show controls active
- Edge Function source tracked in GitHub

## Remaining before Floot retirement

1. Final regression test on iPhone.
2. Final regression test on iPad if it is part of normal use.
3. Confirm progress created on one device appears on another.
4. Confirm one real accounting AI import can be reviewed and published.
5. Enable leaked-password protection in Supabase Auth if available.
6. Keep Floot untouched until the checks above pass.
7. Retire Floot only after GitHub Pages is confirmed as the sole canonical deployment.
