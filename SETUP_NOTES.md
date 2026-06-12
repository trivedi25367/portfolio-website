# Setup Notes

## Local run

```powershell
cd django-tailwind-blog-main
python -m venv env
.\env\Scripts\activate
python -m pip install --upgrade pip setuptools wheel
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

Open `http://127.0.0.1:8000`.

## Before deployment

Set these environment variables on your hosting platform:

- `DJANGO_SECRET_KEY`
- `DJANGO_DEBUG=False`
- `DJANGO_ALLOWED_HOSTS=your-domain.com`
- `EMAIL_HOST_USER`
- `EMAIL_HOST_PASSWORD`
- `DEFAULT_FROM_EMAIL`
- `CONTACT_RECIPIENT_EMAIL`

Do not commit real passwords or app passwords into `settings.py`.

## Notes

The original zip included a local SQLite database and generated files. They are useful for local preview, but a clean public project should not include private databases, `__pycache__`, `.pyc`, `node_modules`, or generated `staticfiles`.

This cleaned version uses modern dependency ranges for newer Python versions. If you already created an `env` folder before this update, delete that folder and create it again before installing requirements.
