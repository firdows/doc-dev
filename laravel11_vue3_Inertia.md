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

3. Install npm vue3
   https://inertiajs.com/client-side-setup
   ```
   npm install @inertiajs/vue3
   ```

   resources/js/app.js
   ```
    import './bootstrap';
    import { createApp, h } from 'vue'
    import { createInertiaApp } from '@inertiajs/vue3'
    
    createInertiaApp({
      resolve: name => {
        const pages = import.meta.glob('./Pages/**/*.vue', { eager: true })
        return pages[`./Pages/${name}.vue`]
      },
      setup({ el, App, props, plugin }) {
        createApp({ render: () => h(App, props) })
          .use(plugin)
          .mount(el)
      },
    })
   ```

4. install cofig 
    https://github.com/vitejs/vite-plugin-vue/tree/main/packages/plugin-vue
    ```
    import vue from '@vitejs/plugin-vue';
    ```

5. run or bulid
  ```
  npm run dev
  or
  npm run build
  ```


6. install bootstrap
   https://www.youtube.com/watch?v=ukF9v3bByCU
   https://www.youtube.com/watch?v=Egtbegv1NhY
  ```
  npm install bootstrap
  npm install -D sass-embedded
  ```

   
   
8. 
   

