<p align="center">
  <img src="https://img.shields.io/badge/Application-Full%20Stack-black" />
  <img src="https://img.shields.io/badge/Backend-Flask-000000?logo=flask&logoColor=white" />
  <img src="https://img.shields.io/badge/Frontend-Vue.js-42B883?logo=vue.js&logoColor=white" />
</p>

# Capstone Project

Conversate is a full-stack portfolio project that demonstrates secure authentication, interactive flashcards, and translation features in a language learning web application. The backend is powered by Flask and PostgreSQL with migrations managed through Alembic, while the frontend uses Vue.js with Auth0 integration.

## Screenshot
![App Screenshot](./screenshot.png)

## Features

Authentication with Auth0 (secure login/logout, profile handling).  
Backend API built with Flask + SQLAlchemy, migrations managed by Flask-Migrate (powered by Alembic).  
Frontend built in Vue.js with Vue Router and Auth0 integration.  
CRUD operations for lessons, flashcards, and user profiles.  
Database migrations using Alembic to evolve schema over time.  
Demo ready: local environment spins up with `python manage.py runserver` (backend) and `npm run serve` (frontend).  

## Tech Stack

**Backend**
- Python 3.9  
- Flask 1.1  
- Flask-Migrate + Alembic  
- Flask-SQLAlchemy  
- PostgreSQL  
- Gunicorn (production ready WSGI server)  

**Frontend**
- Vue.js 2  
- Vue Router  
- Auth0 SPA SDK  
- Sass for styling  

## Installation

### Backend

#### Clone repository
git clone https://github.com/ryanhillman/capstone-project.git
cd capstone-project/backend

#### Create and activate virtual environment
python3.9 -m venv venv

##### Windows
venv\Scripts\activate

##### Mac/Linux
source venv/bin/activate

#### Install dependencies
pip install -r requirements.txt

#### Configure environment variables
FLASK_APP=app.py
FLASK_ENV=development
DATABASE_URL=postgresql://username:password@localhost:5432/capstone_db
AUTH0_DOMAIN=your-auth0-domain
AUTH0_CLIENT_ID=your-client-id
AUTH0_CLIENT_SECRET=your-client-secret

#### Run database migrations
python manage.py db upgrade

#### Start backend
python manage.py runserver

The backend will run on: 

http://127.0.0.1:5000

### Frontend
cd capstone-project/frontend

#### Install dependencies
npm install

#### Configure environment variables
VUE_APP_AUTH0_DOMAIN=your-auth0-domain
VUE_APP_AUTH0_CLIENT_ID=your-client-id
VUE_APP_AUTH0_AUDIENCE=http://localhost:5000

#### Run development server
npm run serve

The frontend will run on: 

Local: http://localhost:3000
(works with Auth0)

Network: http://<your-ip>:3000
(may show Auth0 error: requires HTTPS/secure origin)

## Known Limitations

Auth0 requires secure origins.

Works with http://localhost:3000

Fails on http://<LAN-IP>:3000 unless HTTPS is configured

Some deprecated dependencies may show warnings (e.g., sass-loader, legacy-js-api).


