# Campus Care 360 — Vercel Beginner Version

Campus complaint and emergency management system built with Flask.

## Login email rule

Only email addresses ending with `@campus.360` are accepted.

Examples:
- `student1@campus.360`
- `jashwanth@campus.360`

Accounts are created through registration. Admin access is configured with Vercel environment variables.

## Create an admin account on Vercel

Do not put the admin password in `app.py` or GitHub. In Vercel, add these Environment Variables:

- `ADMIN_EMAIL` = an approved address ending in `@campus.360`
- `ADMIN_PASSWORD` = your private admin password
- `ADMIN_NAME` = Campus Administrator (optional)
- `ADMIN_MOBILE` = admin mobile number (optional)

The app creates that admin account automatically when the database is initialized.

## Vercel settings

- Application Preset: Other
- Root Directory: `./`
- Build Command: leave empty
- Output Directory: leave empty
- Install Command: `pip install -r requirements.txt`

Keep `app.py` and `requirements.txt` in the repository root.
