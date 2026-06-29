# Portfolio Website (Flask + SQLite)

Brief portfolio site with a dark two-column layout, simple sign-up / sign-in, and SQLite storage. Uses a Python `venv` and Flask for the backend.

**Structure**
- `app.py`: Flask application serving the frontend and auth endpoints.
- `init_db.py`: Initialize the `database.db` SQLite database and create the `users` table.
- `templates/index.html`: Main frontend template.
- `static/css/style.css`: Styles matching the provided design.
- `static/js/main.js`: Frontend JS handling modal, signup and signin requests.
- `database.db`: SQLite file (created by `init_db.py`).

**Setup (Windows)**
1. Create a virtual environment:

```powershell
python -m venv venv
.\n+venv\Scripts\Activate.ps1
```

2. Install dependencies:

```powershell
pip install -r requirements.txt
```

3. Initialize the database:

```powershell
python init_db.py
```

4. Run the app:

```powershell
python app.py
```

Open http://127.0.0.1:5000 in your browser.

**Endpoints**
- `GET /` — Portfolio page
- `POST /signup` — Create account. Accepts JSON `{username,password}`
- `POST /signin` — Sign in. Accepts JSON `{username,password}`
- `POST /signout` — Sign out
- `GET /profile` — Returns simple profile JSON when signed in

**Notes & Next Steps**
- Replace `app.secret_key` with a secure random value in production.
- Add CSRF protection and input validation for production readiness.
- Add media and optimize images under `static/`.
