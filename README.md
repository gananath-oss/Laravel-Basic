# Laravel Note Web App

A basic note-taking web application built with Laravel, implementing full CRUD functionality and user authentication using Laravel Breeze. This app ensures that only authenticated users can view, create, update, and delete their own notes. Custom error pages are also added for a better user experience.

## Features

- **User Authentication**: Users can register, login, and manage their account securely using Laravel Breeze.
- **CRUD for Notes**: Users can create, read, update, and delete their personal notes.
- **User-Specific Data**: Each user can only access their own notes; other users' notes are not visible.
- **Custom Error Pages**: Tailored 403 and 404 error pages for better user experience.

## Technologies Used

- **Backend**: Laravel 11
- **Frontend**: Blade Templates (with Tailwind CSS)
- **Authentication**: Laravel Breeze
- **Database**: MySQL / SQLite (depending on your configuration)
- **Error Handling**: Custom error views for forbidden, not found, and server errors

## Installation

### Prerequisites
- PHP 8.x
- Composer
- MySQL / SQLite
- Node.js & npm

### Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/laravel-note-app.git
   cd laravel-note-app
   ```

2. **Install Dependencies**
   ```bash
   composer install
   npm install
   ```

3. **Environment Setup**
   Copy `.env.example` to `.env` and configure your database:
   ```bash
   cp .env.example .env
   ```
   Update the `.env` file to match your database settings:
   ```dotenv
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=your_database_name
   DB_USERNAME=your_database_user
   DB_PASSWORD=your_database_password
   ```

4. **Generate Application Key**
   ```bash
   php artisan key:generate
   ```

5. **Run Migrations**
   ```bash
   php artisan migrate
   ```

6. **Build Frontend Assets**
   ```bash
   npm run dev
   ```

7. **Serve the Application**
   ```bash
   php artisan serve
   ```

   Visit the application at `http://127.0.0.1:8000`.

## Usage

1. **User Registration & Login**: New users can register and log in.
2. **Create Notes**: After logging in, users can create notes.
3. **View Notes**: Only logged-in users can see their own notes.
4. **Edit and Delete Notes**: Users can edit or delete their existing notes.

## Custom Error Pages

- **403 Forbidden**: Shown when a user tries to access notes that aren't theirs.
- **404 Not Found**: Displayed for invalid URLs.

## Project Structure

- `app/Http/Controllers/NoteController.php`: Handles the CRUD logic for notes.
- `resources/views/notes/`: Blade templates for displaying the notes interface.
- `routes/web.php`: Defines the routes for CRUD operations and user access.
- `resources/views/errors/`: Contains custom error views for 403, 404, and 500.
