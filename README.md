Laravel5 / MySQL5.7 / PHP5.6
===============================================

1. docker up

  ```
  $ docker-compose up -d
  ```

2. Laravel Database Migrate

  ```
  $ docker-compose exec app bash
  [root /]# php artisan migrate
  ```

Make Step Laravel Project
-------------------------------------------------

1. install laravel

  ```
  $ composer global require "laravel/installer"
  ```

2. craete laravel project

  ```
  $ laravel new laravel5
  ```

3. modify database configuration

   Overwrite `laravel5/.env`

   ```
   DB_HOST=mysql
   DB_DATABASE=laravel
   DB_USERNAME=my_user
   DB_PASSWORD=my_password
   ```
