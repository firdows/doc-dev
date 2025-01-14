# Laravel 11 with Inertia Js and Vue Js
https://www.youtube.com/watch?v=iGnlmxA7oM8&list=PL38wFHH4qYZXCW2rlBLNdHi5cv-v_qlXO


1. Install Laravel
  ```
  composer create-project laravel/laravel my-project
  ```
  or
  ```
  composer global require laravel/installer
  laravel new
  Enter project name
  ```

2. Install Inertia
  https://inertiajs.com/server-side-setup
  ```
  composer require inertiajs/inertia-laravel
  php artisan inertia:middleware
  ```

  resources/views/app.blade.php
  ```
  <!DOCTYPE html>
  <html>
    <head>
      <meta charset="utf-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0" />
      @vite('resources/js/app.js')
      @inertiaHead
    </head>
    <body>
      @inertia
    </body>
  </html>
  ```

  boostap/app.php
  ```
  use App\Http\Middleware\HandleInertiaRequests;

  ->withMiddleware(function (Middleware $middleware) {
      $middleware->web(append: [
          HandleInertiaRequests::class,
      ]);
  })
  ```
