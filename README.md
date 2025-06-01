
# Laravel 9 Event-Booking API

A simple RESTful API built with Laravel 9 using JSON Web Tokens (JWT) for Event -Booking.

## 🔧 Features

- User registration
- User login with JWT
- Token-based authentication
- Secure route access using middleware
- Laravel 9 and Tymon JWTAuth integration

## 🛠️ Requirements

- PHP >= 8.0
- Composer
- Laravel 9
- MySQL or any supported DB
- WAMP/XAMPP/Laragon (or your preferred local server)

## 🚀 Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/event-booking
cd event-booking
```

2. Install dependencies:

```bash
composer install
```

3. Copy `.env` file:

```bash
cp .env.example .env
```

4. Generate application key:

```bash
php artisan key:generate
```

5. Configure your database in `.env`:

```env
DB_DATABASE=your_db
DB_USERNAME=root
DB_PASSWORD=
```

6. Run migrations:

```bash
php artisan migrate
```

7. Install JWT package:

```bash
composer require tymon/jwt-auth
```

8. Publish JWT config:

```bash
php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\LaravelServiceProvider"
```

9. Generate JWT secret:

```bash
php artisan jwt:secret
```

10. Serve the app:

```bash
php artisan serve
```

## 📬 API Endpoints

| Method | Endpoint        | Description         |
|--------|-----------------|---------------------|
| POST   | `/api/register` | Register a new user |
| POST   | `/api/login`    | Login and get token |
| GET    | `/api/user`     | Get authenticated user (requires token) |

## 🛡️ Secure Routes

Add `auth:api` middleware to protect routes:

```php
Route::middleware('auth:api')->get('/user', function (Request $request) {
    return $request->user();
});
```

## 📂 Folder Structure

```
app/Http/Controllers/API/AuthController.php
config/auth.php
routes/api.php
```

## 📖 License

This project is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
