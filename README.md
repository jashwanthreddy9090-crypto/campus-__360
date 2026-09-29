# Campus Care 360 - Vercel Beginner Version

This is a Flask + SQLite campus complaint management project.

## Files

- `app.py` - the main Flask application
- `requirements.txt` - Python packages Vercel installs
- `.gitignore` - files that should not be uploaded to GitHub

There is intentionally **no `api/` folder and no `vercel.json`**. Current Vercel supports Flask with zero configuration.

## 1. Test on your computer

Open Command Prompt in this folder:

```text
py -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
py app.py
```

Open:

```text
http://127.0.0.1:5000
```

Demo student:

```text
student@campuscare.com
student123
```

Demo admin:

```text
admin@campuscare.com
admin123
```

## 2. Upload to GitHub

The GitHub repository root should look like:

```text
campus-360/
├── app.py
├── requirements.txt
├── .gitignore
└── README.md
```

Do not put these files inside another `CampusCare360-Vercel-Beginner` folder.

## 3. Deploy on Vercel

1. Go to Vercel and choose **Add New -> Project**.
2. Import your GitHub repository.
3. Project name: `campus-360` (or another available name).
4. Application Preset: if **Flask** is not shown, leave it as **Other**. Vercel detects Flask automatically.
5. Root Directory: `./`
6. Do not add a Build Command.
7. Do not add an Output Directory.
8. Click **Deploy**.

## 4. Optional but recommended: SECRET_KEY

In Vercel Project Settings -> Environment Variables add:

```text
Name: SECRET_KEY
Value: use-a-long-random-secret-string-here
```

Then redeploy.

## Important storage note

This version uses SQLite and `/tmp` on Vercel so the application can run without filesystem errors. Vercel's runtime storage is temporary, so database records and uploaded images are **not guaranteed to survive across new deployments or runtime instances**.

For a real production version where complaints and images must stay permanently, move the database to a managed PostgreSQL service and images to object storage such as Vercel Blob, Supabase Storage or Cloudinary.
