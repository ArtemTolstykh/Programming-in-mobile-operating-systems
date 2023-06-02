Примонтировал volume:

docker run -d -p 8080:80 -v /usr/local/my-site:/usr/share/nginx/my-site/html nginx

Для генерации произвольных таблиц в PostgreSQL можно использовать SQL-скрипты, как было описано выше. Например, чтобы создать таблицу пользователей, можно выполнить следующий SQL-запрос:
Использовал SQL скрипт для генерации таблицы с пользователями

CREATE TABLE users (
  id serial PRIMARY KEY,
  name varchar(50) NOT NULL,
  age smallint
);
После этого можно заполнить таблицу данными при помощи команды INSERT.

Для запуска контейнера Nginx с монтированием volume и измененным конфигурационным файлом нужно выполнить команду:

docker run -d -p 8080:80 -v /usr/local/nginx.conf:/etc/nginx/nginx.conf:ro -v /path/to/local/folder:/usr/share/nginx/my-site/html nginx

curl http://localhost:8080/