# Citron System
Данная система разработана для систематизации процессов в различных проектах.

Полная документация: https://alecmei-gubin.gitbook.io/citron-system/
## Развертывание приложения
Первым делом необходимо склонировать проект: 

```
$ git clone https://github.com/WebMad/citron.git
```

После клонирования делаем стандартную настройку:

```
$ composer update
```

Далее настройте подключение к базе данных и установите начальные настройки приложения. Cкопируйте файл `example.env` и переименуйте его в `.env`

```
DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=2506
DB_DATABASE=<ИМЯ ВАШЕЙ БАЗЫ ДАННЫХ>
DB_USERNAME=<ПОЛЬЗОВАТЕЛЬ>
DB_PASSWORD=<ПАРОЛЬ>
```

Теперь необходимо провести миграцию и заполнить базу данных:

```
$ php artisan migrate --seed
```


Затем сгенерируйте ключ приложения и ключ для laravel/passport авторизации

```
$ php artisan key:generate
$ php artisan passport:install
```

Поздравляю! Теперь тебе просто необходимо открыть проект в браузере
