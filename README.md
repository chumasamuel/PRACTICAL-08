# PRACTICAL 08 — Laravel Foundations: Routes, Controllers and Blade

Student: Samuel Chuma  
Register Number: ____________________  
Practical Number: 08  
Technology: PHP + Laravel  
Mode: Individual

## Compatibility
This corrected project uses **Laravel 9.x** and requires **PHP 8.0.2+**. It is intended to work with XAMPP PHP 8.0.x.

## Run in VS Code

Open the folder containing `artisan` and `composer.json`, then:

```cmd
composer install
copy .env.example .env
php artisan key:generate
php artisan optimize:clear
php artisan route:list
php artisan serve
```

Open `http://127.0.0.1:8000`.

If `php` is not recognized, use:

```cmd
C:\xampp\php\php.exe artisan key:generate
C:\xampp\php\php.exe artisan optimize:clear
C:\xampp\php\php.exe artisan route:list
C:\xampp\php\php.exe artisan serve
```

## Pages
- `/` — Home
- `/about` — About
- `/courses` — Courses
- Any invalid URL — custom 404

## Requirements demonstrated
1. Laravel project and environment template.
2. Home, About and Courses routes handled by `PageController`.
3. Reusable Blade layout with navigation, content and footer.
4. Course array passed by controller and rendered with `@foreach`.
5. Empty state, named routes, active navigation and custom 404.

## Request flow

```text
Browser
  ↓
routes/web.php
  ↓
Named Route
  ↓
PageController
  ↓
Blade View
  ↓
HTML Response
  ↓
Browser
```

For Courses:

```text
Browser → Route → PageController::courses()
        → $courses array → courses.blade.php
        → @foreach → Course Cards → Browser
```

## Evidence
Take screenshots of:
- Home
- About
- Courses
- Custom 404
- `php artisan route:list`
- VS Code project structure
- `php artisan serve`

## Submission
Do not submit `.env` or `vendor/`. Submit `.env.example`, source code, README and screenshots.

## If Composer shows curl error 6 / proxy
That indicates Composer cannot reach Packagist because of DNS/network/proxy settings. Check:

```cmd
composer diagnose
composer config --global --list
```

The Laravel source code is already prepared for PHP 8.0.x; the first dependency installation still requires Composer network access.
