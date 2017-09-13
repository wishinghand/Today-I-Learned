# Installing Laravel

If Laravel has a "Whoops" error on your website, turn debugging on in $app/config/app.php:

`'debug' => env('APP_DEBUG', false) -> 'debug' => env('APP_DEBUG', true),`

- `cp .env.example .env`
- `php artisan key:generate`