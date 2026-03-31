Task Manager
<img width="1366" height="693" alt="ui" src="https://github.com/user-attachments/assets/6e1cd2c7-e077-47e6-872d-43532b4ff19c" />


A full-stack Task Manager application built with Laravel 12 (PHP) for the backend and Vue 3 + Vite for the frontend.
This project demonstrates RESTful API design, task CRUD operations, status management, and daily reporting. It’s designed to showcase clean code, best practices, and real-world development workflows.

🌟 Features
✅ Create, update, delete, and view tasks
✅ Update task status following allowed transitions: pending → in_progress → done
✅ Filter tasks by status and priority
✅ Task summary report grouped by priority and status
✅ Clean RESTful API endpoints
✅ Vue 3 frontend with responsive, mobile-friendly UI (optional)
✅ Supports PostgreSQL and MySQL databases
✅ Docker-ready for local development
🛠 Requirements
PHP >= 8.2
Composer
Node.js >= 18
PNPM or NPM
PostgreSQL or MySQL database
Git
🚀 Local Setup
1. Clone the repository
git clone https://github.com/joseph-musyoki/taskmanager.git
cd taskmanager
2. Copy & configure .env
cp .env.example .env

Edit .env to match your database credentials:

APP_NAME=TaskManager
APP_ENV=local
APP_KEY=
APP_DEBUG=true
APP_URL=http://localhost:8000

DB_CONNECTION=mysql
DB_DATABASE=task_manager
DB_USERNAME=root
DB_PASSWORD=
DB_PORT=3306

⚠️ Note: For MySQL, update DB_CONNECTION and credentials as needed. For PostgreSQL, change DB_CONNECTION=pgsql and update port/username/password.

3. Install PHP dependencies
composer install

Generate the application key:

php artisan key:generate
4. Run Database Migrations

Create your database first (MySQL example):

mysql -u root -p
CREATE DATABASE task_manager;

Run Laravel migrations:

php artisan migrate

Optional: seed demo data (if seeds exist):

php artisan db:seed
5. Install Frontend Dependencies
pnpm install
# or using npm
npm install
6. Compile Frontend (Vue + Vite)

Development mode:

npm run dev

Open your browser:

http://localhost:5173/

Production build:

pnpm run build

This generates a dist/ folder ready for deployment.

7. Run Laravel Server
php artisan serve

Open your browser:

http://127.0.0.1:8000

API base URL: http://127.0.0.1:8000/api/tasks
<img width="734" height="447" alt="image" src="https://github.com/user-attachments/assets/34731ff5-8720-40b2-b5f0-1530ca0a7258" />
<img width="600" height="205" alt="ui-run command" src="https://github.com/user-attachments/assets/161bc6f2-0a0e-40ae-84be-f21865c89f59" />



📌 API Endpoints
Method	Endpoint	Description
GET	/api/tasks	List all tasks
POST	/api/tasks	Create a new task
PATCH	/api/tasks/{id}/status	Update task status
DELETE	/api/tasks/{id}	Delete a task (only if status is done)
GET	/api/tasks/report?date=YYYY-MM-DD	Task summary report by priority and status
