Build for php with php 8.2 + nginx latest (1.23) + mysql 8.0 + phpmyadmin 5

Сборка для 2х проектов в среде php-mysql-nginx

Папка для веб-проектов - projects. В ней 2 папки - для обычного проекта и для проекта на yii2 - пути для веб-сервера настроены соответственно. Проект на yii2 доступен по 80 порту, второй проект висит на 8080.

Настройки веб-сервера лежат в папке \nginx\conf.d\vhost.conf Настройки php в \php-server\Dockerfile Можно подкинуть файл php.ini, он в \php-server\php\php.ini Переменные среды в .env Небольшие конфиги для mysql в \db\mysql\my.cnf

Установка:

в консоли переходим в папку контейнера
запускаем билд docker-compose build
поднимаем сборку docker-compose up
