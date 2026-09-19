# CodeAlpha Tasks

Projects submitted by **Dhiraj Kumar Verma** for the CodeAlpha internship.

## Included project

| Project | Source code | Technologies | Demo |
| --- | --- | --- | --- |
| Student Activity Tracker | [Open project folder](student-activity-tracker/) | Python, Flask, MySQL, HTML, CSS, JavaScript, Jinja, Chart.js | [Live website](https://student-activity-tracker-production.up.railway.app) |

## Student Activity Tracker

A web application that helps students record study sessions, project work, and other daily activities, then review how they spend their time.

### Features

- Account registration, password hashing, login, and logout.
- Add, edit, and delete activities with category, duration, and date.
- Dashboard totals for activities, minutes, hours, and today's progress.
- Daily and category-based progress charts.
- Filter history by category and date, and export the results as CSV.
- Create and rename categories, or remove a category from your own choices while keeping saved activity history.
- Responsive pages with MySQL persistence.

Category creation and renaming use a shared catalog; category removal is saved per account.

### Run locally

You need Python, pip, and a running MySQL server.

1. Clone this repository and enter the project folder:

   ```bash
   git clone https://github.com/Dhiraj288/codealpha_tasks.git
   cd codealpha_tasks/student-activity-tracker
   python -m venv .venv
   ```

2. Activate the environment:

   Windows PowerShell:

   ```powershell
   .\.venv\Scripts\Activate.ps1
   ```

   macOS / Linux:

   ```bash
   source .venv/bin/activate
   ```

3. Install the project dependencies:

   ```bash
   python -m pip install -r requirements.txt
   ```

4. In MySQL, create a local database:

   ```sql
   CREATE DATABASE IF NOT EXISTS study_tracker;
   ```

5. Copy `.env.example` to `.env` in the project folder. Set your local database credentials and generate your own session key:

   ```bash
   python -c "import secrets; print(secrets.token_hex(32))"
   ```

   Paste the generated value after `SECRET_KEY=` in your local `.env`. Do not commit the real file.

6. Initialize the tables and start the development server:

   ```bash
   python init_db.py
   python app.py
   ```

7. Open `http://127.0.0.1:5000`, register an account, and add an activity.

### Existing regression checks

```bash
python -m unittest discover -s tests -v
```

These checks use disposable SQLite data through a MySQL adapter. They do not connect to the live database. The development server is for local use; the separate Railway deployment uses Gunicorn.

## Project links

- [Original project repository](https://github.com/Dhiraj288/student-activity-tracker)
- [Live Student Activity Tracker](https://student-activity-tracker-production.up.railway.app)
- [Developer's GitHub profile](https://github.com/Dhiraj288)

The project folder contains a source snapshot from commit `9bb2625617b676eb790c0ab2c0f648fa99818ff3` of the original repository. This submission repository does not contain account data or database credentials.
