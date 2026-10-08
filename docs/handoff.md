# Handoff / next actions

Current GitHub account: `Phuong301CP`.

Blocking item: the connected GitHub integration cannot create a new repository, and the account currently exposes no repositories. Create a repository named `icaew-lms`; then the migration package can be pushed directly through the connected GitHub integration.

After the repo exists:

1. Upload all prepared repo files.
2. Verify `main` branch.
3. Enable GitHub Pages with GitHub Actions.
4. Wait for first Pages workflow run and inspect logs if it fails.
5. Set Supabase Auth Site URL and allowed redirect URLs to the Pages URL.
6. Test login on desktop + iPhone.
7. Test cloud progress sync.
8. Test Admin CMS question publish.
9. Test Lessons publish/read.
10. Configure AI Import Edge Function provider secret and test image/PDF import.
11. Keep Floot live until all above pass; then retire it.