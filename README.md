# Student Management System

A simple and beginner-friendly Laravel application for managing student records with full CRUD (Create, Read, Update, Delete) functionality.

## Features

- **Add Student** - Create new student records with name, email, and course
- **View Student List** - Display all students in a responsive table
- **Edit Student** - Update existing student information
- **Delete Student** - Remove student records with confirmation
- **Form Validation** - Input validation for all form fields
- **Success Messages** - Feedback notifications after each operation

## Technologies Used

- **Backend:** Laravel 11 (PHP 8.2+)
- **Database:** SQLite (for simplicity) / MySQL (configurable)
- **Frontend:** Blade Templates with Bootstrap 5
- **Version Control:** Git

## Prerequisites

Before running this project, make sure you have:

- PHP 8.2 or higher
- Composer installed
- Laravel installer (optional)

## Installation

Follow these steps to set up the project on your local machine:

### 1. Clone the Repository
```bash
git clone https://github.com/kmramar/student-management-system.git
cd student-management-system
```

### 2. Install Dependencies
```bash
composer install
```

### 3. Environment Setup
```bash
# Copy the example environment file
cp .env.example .env

# Generate application key
php artisan key:generate
```

### 4. Database Setup

**For SQLite (Default - Recommended for beginners):**
The database is already configured to use SQLite. Just run:
```bash
touch database/database.sqlite
php artisan migrate
```

**For MySQL:**
1. Create a database named `student_management` in MySQL
2. Update `.env` file:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=student_management
DB_USERNAME=root
DB_PASSWORD=your_password
```
3. Run migrations:
```bash
php artisan migrate
```

### 5. Start the Development Server
```bash
php artisan serve
```

### 6. Access the Application
Open your browser and navigate to:
```
http://127.0.0.1:8000/students
```

## Project Structure

```
student-management-system/
├── app/
│   ├── Http/
│   │   └── Controllers/
│   │       └── StudentController.php    # CRUD operations
│   └── Models/
│       └── Student.php                  # Student model
├── database/
│   └── migrations/
│       └── 2026_03_11_142433_create_students_table.php
├── resources/
│   └── views/
│       ├── layouts/
│       │   └── app.blade.php           # Master layout
│       └── students/
│           ├── index.blade.php          # Student list
│           ├── create.blade.php        # Add student form
│           └── edit.blade.php          # Edit student form
└── routes/
    └── web.php                          # Application routes
```

## Database Schema

The `students` table has the following fields:

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary key, auto-increment |
| name | VARCHAR(255) | Student name |
| email | VARCHAR(255) | Student email (unique) |
| course | VARCHAR(255) | Course name |
| created_at | TIMESTAMP | Creation timestamp |
| updated_at | TIMESTAMP | Update timestamp |

## Available Routes

| Method | URL | Description |
|--------|-----|-------------|
| GET | /students | List all students |
| GET | /students/create | Show add form |
| POST | /students | Store new student |
| GET | /students/{id}/edit | Show edit form |
| PUT | /students/{id} | Update student |
| DELETE | /students/{id} | Delete student |

## Usage

1. **Add Student:** Click "Add New Student" button, fill in the form, and submit
2. **View Students:** See all students in the table on the main page
3. **Edit Student:** Click "Edit" button next to any student
4. **Delete Student:** Click "Delete" button (with confirmation)

## Screenshots

The application features:
- Clean Bootstrap-styled interface
- Responsive table with all student data
- Form validation with error messages
- Success notifications after operations

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

## Author

- **Amar Kumar**
- Email: AmarKumar.official@gmail.com
- GitHub: [kmramar](https://github.com/kmramar)
