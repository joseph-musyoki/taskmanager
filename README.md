# Task Manager

A full-stack Task Manager application built with **Laravel 12** (PHP) and **Vue 3 + Vite** for frontend.  
This project demonstrates RESTful APIs, task CRUD operations, status management, and reporting.

---

## Features

- Create, update, delete, and view tasks
- Update task status with allowed transitions
- Filter tasks by status and priority
- Task summary report by priority and status
- Clean RESTful API endpoints
- Vue 3 frontend with responsive UI (optional)
- PostgreSQL and MySQL database support
- Docker-ready for local development

---

## Requirements

- PHP >= 8.2
- Composer
- Node.js >= 18
- PNPM or NPM
- PostgreSQL or MySQL database
- Git

---

## Local Setup

### 1. Clone the repository

```bash
git clone https://github.com/joseph-musyoki/taskmanager.git
cd taskmanager
2. Copy .env file
cp .env.example .env

Edit .env to match your local database credentials:

APP_NAME=TaskManager
APP_ENV=local
APP_KEY=
APP_DEBUG=true
APP_URL=http://localhost:8000

DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=5432
DB_DATABASE=taskmanager_db
DB_USERNAME=postgres
DB_PASSWORD=secret

Note: For MySQL, set DB_CONNECTION=mysql and update port/credentials accordingly.

3. Install PHP dependencies
composer install

Generate application key:

php artisan key:generate
4. Run Database Migrations

Create your database first (PostgreSQL example):

createdb taskmanager_db

Run Laravel migrations:

php artisan migrate

Optional: seed demo data (if seeds are added):

php artisan db:seed
5. Install Frontend Dependencies
pnpm install
# or using npm:
npm install
6. Compile Frontend (Vue + Vite)

Development mode:

pnpm run dev

Open browser:

http://localhost:5173/

Production build:

pnpm run build

This generates a dist/ folder.

7. Run Laravel Server
php artisan serve

Open browser:

http://127.0.0.1:8000

API base URL:

http://127.0.0.1:8000/api/tasks
API Endpoints
Method	Endpoint	Description
GET	/api/tasks	List all tasks
POST	/api/tasks	Create a new task
PATCH	/api/tasks/{id}/status	Update task status
DELETE	/api/tasks/{id}	Delete a task (only done status)
GET	/api/tasks/report?date=YYYY-MM-DD	Task summary report by priority and status
Project Structure
app/            # Laravel app logic (Controllers, Models)
routes/         # API and web routes
database/       # Migrations and seeds
resources/js/   # Vue 3 frontend
public/         # Public assets
Troubleshooting
Database connection fails → double-check .env and make sure the database service is running
Missing composer dependencies → run composer install
Frontend errors → run pnpm install and pnpm run dev
