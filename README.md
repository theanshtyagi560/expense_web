# Expense Tracker Web App (Django)

A multi-user expense tracker built with Django and SQLite. Week 2 project: web app with authentication and a database, running on localhost.

## Features
- User registration, login, logout (Django auth)
- Each user sees only their own data
- Add, edit, delete income and expenses
- Dashboard with total income, expenses, balance and per-category breakdown
- Filter by type/category, pagination
- Django admin at `/admin/`

## Run locally
```bash
python -m venv venv
venv\Scripts\activate          # Windows  (Mac/Linux: source venv/bin/activate)
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```
Open http://127.0.0.1:8000/ and register an account.

Optional: `python manage.py createsuperuser` for the admin panel.

## Run tests
```bash
python manage.py test
```

## Structure
- `config/` - project settings and root URLs
- `tracker/` - app: `models.py` (Transaction), `views.py` (class-based views), `forms.py`, `urls.py`, `tests.py`
- `templates/` - base layout, auth pages, dashboard and forms

## Security notes
- CSRF protection on all forms; queries scoped by `request.user`
- Set `DJANGO_SECRET_KEY` and `DJANGO_DEBUG=0` for any real deployment
