# ICAEW LMS architecture

```text
GitHub Pages
├── index.html        Quiz LMS
├── admin.html        Admin CMS
└── lessons.html      Theory reader
        │
        ▼
Supabase
├── Auth
├── Postgres
│   ├── subjects
│   ├── chapters
│   ├── exercises
│   ├── questions
│   ├── lessons
│   ├── user_progress
│   ├── user_preferences
│   ├── content_sources
│   └── import_drafts
├── Storage
│   └── content-imports (private)
└── Edge Functions
    └── icaew-ai-import
```

GitHub owns deploy/version control. Supabase owns data and authenticated backend capabilities. Floot is not required after the migration has passed end-to-end tests.