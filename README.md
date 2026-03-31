# Flask Blog Hub

A full-featured blogging platform built with Flask. Users can register, log in, create posts, edit their profiles, and reset passwords. The app is ready for deployment on Render.com.

## Features
- User registration and authentication
- Create, edit, and delete blog posts
- User profile with profile picture upload
- Password reset via email (Gmail/app password required)
- Error handling pages (403, 404, 500)
- Responsive design with custom CSS

## Project Structure
```
flaskblog/
    __init__.py
    config.py
    models.py
    errors/
        __init__.py
        handlers.py
    main/
        __init__.py
        routes.py
    posts/
        __init__.py
        forms.py
        routes.py
    users/
        __init__.py
        forms.py
        routes.py
        utils.py
    static/
        main.css
        profile_pics/
    templates/
        ... (HTML templates)
instance/
run.py
wsgi.py
requirements.txt
render.yaml
.env.example
```

## Local Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/blog-hub.git
   cd blog-hub
   ```
2. Create a virtual environment and activate it:
   ```bash
   python -m venv venv
   venv\Scripts\activate  # On Windows
   # source venv/bin/activate  # On Mac/Linux
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Run the app:
   ```bash
   python run.py
   ```
   Visit [http://localhost:5000](http://localhost:5000)

## Deployment (Render.com)
1. Push your code to GitHub.
2. Create a new Web Service on [Render.com](https://render.com):
   - **Build Command:** `pip install -r requirements.txt`
   - **Start Command:** `gunicorn wsgi:app`
3. Set environment variables:
   - `SECRET_KEY` (generate with `python -c "import secrets; print(secrets.token_hex(32))"`)
   - `SQLALCHEMY_DATABASE_URI` (e.g., `sqlite:////tmp/site.db` or PostgreSQL URL)
   - `FLASK_ENV=production`
   - `EMAIL_USER` and `EMAIL_PASS` (for password reset, optional)
4. Deploy and visit your Render URL (e.g., `https://blog-hub-xxxx.onrender.com`)
