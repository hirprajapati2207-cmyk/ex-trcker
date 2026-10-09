# Personal Expense Tracker (Flask)

A Python and Flask based personal expense tracker, ready to be deployed on Render and hosted on GitHub.

## Local Development
1. Open your terminal in the `expense-tracker-flask` folder.
2. (Optional but recommended) Create and activate a virtual environment:
   ```bash
   python -m venv venv
   venv\Scripts\activate  # On Windows
   # source venv/bin/activate  # On Mac/Linux
   ```
3. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Run the application:
   ```bash
   python app.py
   ```
5. Open `http://localhost:5000` in your web browser.

## GitHub Setup
To upload this to GitHub:
1. Initialize git: `git init`
2. Add files: `git add .`
3. Commit: `git commit -m "Initial commit - Python Flask Expense Tracker"`
4. Create a repository on GitHub, then push your code:
   ```bash
   git remote add origin <your-github-repo-url>
   git branch -M main
   git push -u origin main
   ```

## Render Deployment
This app is fully ready for [Render](https://render.com/).

1. Sign in to Render.
2. Click **New +** and select **Web Service**.
3. Connect your GitHub repository.
4. Render will automatically detect Python. Verify the following:
   - **Build Command:** `pip install -r requirements.txt`
   - **Start Command:** `gunicorn app:app`

### Important Note on Data Storage for Render
This application currently uses SQLite (storing data in `data/expenses.db`).
- **Render Free Tier:** Provides an ephemeral file system. Your database will be reset every time the app deploys or goes to sleep/wakes up.
- **Persistent Data:** To keep your data intact across restarts, you'll want to switch the database to a hosted database like a free PostgreSQL database on Render. Once created, you just update `SQLALCHEMY_DATABASE_URI` in `app.py`.
