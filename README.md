# Contact Management System

A simple contact management system built with Laravel.
The project was developed to practice modern Laravel development concepts including authentication, CRUD operations, PostgreSQL integration, DataTables server-side processing, and structured version control.

---

# Project Description

This application allows authenticated users to manage their personal contacts.

Each user can create, view, edit and delete their own contacts while ensuring that users cannot access data belonging to others.

The system demonstrates a complete development workflow using Laravel, Blade, Bootstrap, TypeScript and PostgreSQL.

---

# Technologies Used

Backend

* PHP 8.2+
* Laravel (latest stable version)
* PostgreSQL
* Eloquent ORM

Frontend

* Blade Templates
* Bootstrap 5
* TypeScript
* Vite
* DataTables

Infrastructure

* Nginx
* Local development environment

---

# Features

* User authentication (register, login, logout)
* Protected routes using Laravel `auth` middleware
* Dashboard for authenticated users
* Full CRUD for contacts
* Contacts associated with authenticated users
* Server-side DataTables integration
* Pagination, search and sorting
* Phone mask implemented with TypeScript
* Soft Deletes for contacts
* Validation using Form Requests
* Database seeders with example data

---

# Database Structure

Table: contacts

Columns

* id
* user_id (foreign key)
* name
* nickname (nullable)
* phone
* notes (nullable)
* deleted_at (soft delete)
* created_at
* updated_at

Relationships

* User **has many** Contacts
* Contact **belongs to** User

---

# Requirements

Before running the project make sure you have installed:

* PHP 8.2+
* Composer
* Node.js and NPM
* PostgreSQL
* Nginx

---

# Installation

Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/contact-system.git
cd contact-system
```

Install backend dependencies

```bash
composer install
```

Install frontend dependencies

```bash
npm install
```

Copy environment file

```bash
cp .env.example .env
```

Generate application key

```bash
php artisan key:generate
```

---

# Database Configuration

Create a PostgreSQL database and update the `.env` file.

Example configuration:

```
DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=5432
DB_DATABASE=contact_system
DB_USERNAME=postgres
DB_PASSWORD=your_password
```

Run migrations

```
php artisan migrate
```

(Optional) Run seeders

```
php artisan db:seed
```

---

# Frontend Build

Run the development server for frontend assets

```
npm run dev
```

For production build

```
npm run build
```

---

# Web Server Configuration

The application is served using **Nginx**.

The virtual host must point to the **public directory**.

Example local domain:

```
http://contacts.localhost
```

---

# Contacts Module

Authenticated users can:

* Create contacts
* View contact details
* Edit contacts
* Delete contacts (Soft Delete)

Important rules:

* Each contact belongs to an authenticated user
* Users can only access their own contacts
* Deleted contacts are hidden from the default listing

---

# Project Structure Overview

Important directories:

```
app/
  Models/
  Http/
    Controllers/
    Requests/

database/
  migrations/
  seeders/

resources/
  views/
  ts/

routes/
  web.php
```

---

# Version Control

The project uses Git with a branch-based workflow.

Main branches

```
main
develop
feature/*
```

Example feature branches

```
feature/project-setup
feature/authentication
feature/base-layout
feature/contacts-crud
feature/datatables
```

Commit examples

```
feat: implement contacts CRUD
fix: correct contact validation
chore: configure project environment
docs: update README
```

---

# License

This project was developed for learning and evaluation purposes.
