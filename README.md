# Online Exam System (Django)

This is a Django-based online examination system with three roles:
- **Admin**
- **Teacher**
- **Student**

## Prerequisites

- **Python**: 3.11+ recommended (works on newer versions as well).
- **pip**: comes with Python
- (Optional) **Git**

> Note: This project originally used an older Django version. It has been updated to **Django 5.x** to be compatible with modern Python (Python 3.13+ removed modules that older Django relied on).

## Quick start (Windows / PowerShell)

From the project root (the folder containing `manage.py`):

```powershell
# 1) Create + activate a virtual environment
python -m venv .venv
.\.venv\Scripts\Activate.ps1

# 2) Install dependencies
python -m pip install --upgrade pip
pip install -r requirements.txt

# 3) Run migrations
python manage.py migrate

# 4) Create an admin user (optional but recommended)
python manage.py createsuperuser

# 5) Start the dev server
python manage.py runserver
```

Then open the app:
- **Home**: `http://127.0.0.1:8000/`
- **Admin**: `http://127.0.0.1:8000/admin/`

## Project structure

- `onlinexam/`: project config (`settings.py`, `urls.py`, `wsgi.py`)
- `exam/`: core app (home page, admin dashboard views, etc.)
- `teacher/`: teacher app (teacher dashboard, teacher actions)
- `student/`: student app (student dashboard, student actions)
- `templates/`: HTML templates
- `static/`: static files (CSS/images if present)

## Common issues

### Logout returns 405 (Method Not Allowed)
If you see `Method Not Allowed (GET): /logout`, it means logout is being triggered via a link (`GET`) but the default Django logout view expects `POST` in newer versions.

This repo is already adjusted so `/logout` works with the existing templates.

### Missing `/background.png` (404)
If you see `Not Found: /background.png`, it means a template is referencing `background.png` directly. This repo uses a gradient background instead, so you should no longer see those requests.

### Email settings
`onlinexam/settings.py` includes SMTP settings. **Do not commit real credentials** and do not use hard-coded passwords.

For local development, consider switching to Django’s console email backend:

```python
EMAIL_BACKEND = "django.core.mail.backends.console.EmailBackend"
```

## Useful commands

```powershell
# Make migrations (when you change models)
python manage.py makemigrations

# Apply migrations
python manage.py migrate

# Django system check
python manage.py check
```

## License

If you want, tell me what license you prefer (MIT/Apache-2.0/GPL/etc.) and I can add a `LICENSE` file.

# TryOut

TryOut is Online Examination website built using **Django** framework of python<br>
