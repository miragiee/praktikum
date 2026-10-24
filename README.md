# Praktikum

Русская версия: [README_Russian.md](README_Russian.md)

## Project Description

Praktikum is a Laravel web application designed to automate the organization of industrial internships between students, universities, and companies.

The main goal of the project is to simplify the search and distribution of students for internships, the processing of company applications, the coordination of agreements between educational institutions and employers, and the management of document flow and event calendars.

The project is suitable for scenarios where:
- a university publishes and organizes internships;
- companies submit applications for hiring students;
- students register, provide their details, and participate in selection;
- an administrator manages directories and the main entities of the system.

## Main Features

### For students
- registration and authentication;
- profile viewing;
- searching and viewing information about companies and universities;
- participation in searching for suitable candidates/students;
- working with internship applications and reservations;
- viewing scheduled events and bookings.

### For companies
- registration and company profile management;
- creating and managing internship applications;
- selecting study directions and required number of students;
- submitting contract requests to the university;
- uploading documents and working with files;
- viewing the calendar and related events.

### For universities
- registration and management of university profiles;
- creating and maintaining internships;
- working with contracts and agreements with companies;
- managing students and training directions;
- viewing activity calendars and contractual requests.

### For administrators
- managing directories: companies, universities, students, directions;
- managing internships, documents, contracts, and applications;
- monitoring reservations and contract requests;
- supporting the administrative interface of the system.

## User Roles

The system uses a role model:
- student;
- company;
- university;
- administrator.

The relationship between users and entities is implemented through the `User`, `Student`, `Company`, `University`, `Role`, and related classes.

## Technology Stack

| Frontend | Backend | Database |
| :---: | :---: | :---: |
| <img src="https://skillicons.dev/icons?i=html,css,js&theme=dark&perline=10"> | <img src="https://skillicons.dev/icons?i=php,laravel&theme=dark&perline=10"> | <img src="https://skillicons.dev/icons?i=mysql&theme=dark&perline=10"> |

## Project Structure

```text
praktikum/
├── app/
│   ├── Console/
│   ├── Http/
│   │   ├── Controllers/
│   │   ├── Middleware/
│   │   └── Requests/
│   ├── Models/
│   ├── Notifications/
│   └── Providers/
├── bootstrap/
├── config/
├── database/
│   ├── factories/
│   ├── migrations/
│   └── seeders/
├── public/
├── resources/
│   ├── css/
│   ├── js/
│   └── views/
├── routes/
│   ├── web.php
│   └── console.php
├── storage/
├── tests/
├── .env.example
├── artisan
├── composer.json
├── package.json
├── phpunit.xml
├── vite.config.js
├── README.md
├── README_Russian.md
└── vendor/
```

## Key System Entities

### User
The main authentication entity. Each user is linked to a role and may have related records:
- student;
- company;
- university.

### Student
Contains student data: full name, course, field of study, university, email, qualities, and skills.

### Company
Describes a partner company: name, tax ID, website, description, and contact information.

### University
Describes a university, its contact person, tax ID, description, and interaction details.

### Direction
Training direction (for example, programming, design, engineering, etc.).

### Internship
An intermediate practice entity associated with a university and its dates.

### CompanyRequest
A company application for hiring students for a specific field and internship.

### ContractRequest
A request to conclude a contract between a company and a university.

### Reservation
A reservation of a student for an internship/practical placement.

### Document
Documents uploaded and associated with applications or contractual activity.

## Main Application Routes

The project uses routing in `routes/web.php`. Main sections include:

- public pages: home, registration, login, student search;
- user area after login: student, company, and university profiles;
- operations for applications, documents, contracts, and reservations;
- admin section with CRUD operations for core entities.

Examples of key routes:
- `/` — home page;
- `/auth` — login form;
- `/register` — registration;
- `/profile/student` — student profile;
- `/profile/company` — company profile;
- `/profile/university` — university profile;
- `/admin` — admin panel;
- `/internships` — internships list;
- `/partnerships` — partnerships section;
- `/students-in-search` — public student search.

## Requirements for Running

Before launching, make sure the following are installed:
- PHP 8.3+
- Composer
- Node.js and npm
- SQLite or MySQL database
- Git

## Installation and Launch

### 1. Clone the repository

```bash
git clone https://github.com/miragiee/praktikum
cd praktikum
```

### 2. Install PHP dependencies

```bash
composer install
```

### 3. Install JavaScript dependencies

```bash
npm install
```

### 4. Configure environment

Copy the environment example file:

```bash
copy .env.example .env
```

If SQLite is used, the `.env` file already contains:

```env
DB_CONNECTION=sqlite
```

For SQLite, the default settings are usually sufficient if the database is created automatically:

```bash
php artisan migrate
```

### 5. Generate the application key

```bash
php artisan key:generate
```

### 6. Run migrations

```bash
php artisan migrate
```

### 7. Start the application

For local development:

```bash
php artisan serve
```

For frontend development with Vite:

```bash
npm run dev
```

Or use the project script:

```bash
composer run dev
```

## Frontend Build

For a production build:

```bash
npm run build
```

## Validation and Testing

Run tests:

```bash
php artisan test
```

You can also use the script from `composer.json`:

```bash
composer run test
```

>[!important] Admin login data
> Login: admin@admin.com
> Password: password

## Typical Usage Scenario

1. An administrator or developer creates directories such as directions, companies, and universities.
2. The university creates an internship and publishes it in the system.
3. A company submits an application for the required number of students in a selected field.
4. A student registers and selects a suitable internship/company.
5. The system records contract requests between the company and the university.
6. After approval, an intern is assigned, documents are uploaded, and event records are maintained.
7. The administrator monitors the status of applications, reservations, and contracts.

## Security and Privacy

The project uses standard Laravel mechanisms for:
- user authentication;
- password hashing;
- session handling;
- protected routes and middleware.

Important: before deploying to production, it is recommended to:
- configure a real `DB_CONNECTION` and secure database parameters;
- configure SMTP/email notifications;
- enable proper HTTPS support;
- verify access rights for users and administrators.

## Useful Commands

```bash
# Clear cache
php artisan cache:clear
php artisan config:clear
php artisan route:clear

# Check route list
php artisan route:list

# Create a new controller
php artisan make:controller NameController

# Create a new model
php artisan make:model Name
```

## Conclusion

The project is a ready-to-use platform for managing internships and facilitating interaction among participants in the educational process. Its architecture is based on Laravel and is easily extensible thanks to standard MVC, routing, migration, and Blade-template mechanisms.

Because roles and business logic are separated, the application is convenient both for academic purposes and as a demonstration of a working model for coordinating internships between universities and companies.
