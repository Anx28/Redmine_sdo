# Поднятие redmine
redmine+nginx+mysql+cerboot

1) Склонировать репозиторий
2) Создайте файлы .env и database.yml
3) Отредактируйте их
4) Выполните команду  `docker-compose up -d`

Пример .env
```
MYSQL_ROOT_PASSWORD=root_password
MYSQL_DATABASE=redmine
MYSQL_USER=redmine_user
MYSQL_PASSWORD=redmine_password
```

Пример databese.yml
```
production:
  adapter: mysql2
  database: redmine
  host: db
  username: redmine_user
  password: redmine_password
  encoding: utf8
```

Для получение сертификатов, выполните 
```
docker exec -it redmine_certbot certbot certonly --webroot -w /var/www/certbot -d you_domen.com
```
Затем замените nginx.conf (настройте nginx.conf  для работы с HTTPS)
