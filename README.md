# Campus Care — Vercel version

This is the Vercel-compatible version of the Flask Campus Care app.

## Deploy

1. Put this folder in a GitHub repository.
2. In Vercel, import the repository.
3. Vercel should detect the Python function from `api/index.py`.
4. Deploy.
5. Add a `SECRET_KEY` environment variable in Vercel for production sessions.

## Important data note

This version uses `/tmp/campuscare` for SQLite and uploaded images because Vercel serverless functions do not provide a persistent writable local filesystem. The app will deploy and run, but database records and uploaded images are **not guaranteed to persist** between serverless instances.

For a real production Campus Care system, connect the same application to an external PostgreSQL database and object storage for images. The code already supports `DATABASE_PATH` and `UPLOAD_FOLDER` environment variables for non-Vercel deployments.

## Local run

```bash
pip install -r requirements.txt
python app.py
```

Then open `http://127.0.0.1:5000`.

## Demo accounts

Student: `student@campuscare.com` / `student123`

Admin: `admin@campuscare.com` / `admin123`

Change the demo passwords and secret key before using the application beyond a classroom demo.
