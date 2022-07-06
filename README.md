# Описание
Api v1 для проекта api_YaMDb<br>
Обернутая в Docker контейнер

![YAmDB](https://github.com/AlexKing777111/yamdb_final/actions/workflows/yamdb_final.yml/badge.svg)

# Стек технологий

При разработке использован следущий стек технологий:

Python 3.7<br>
Django 2.2.19<br>
Django Rest Framework<br>
PstgreSQL

# Установка
1. Проверьте версию docker и убедитесь что он установлен, командой:
 ```
 docker -v 
 ```
2. Склонировать репозиторий командой:
 ```
 git@github.com:AlexKing777111/infra_sp2.git
 ```
3. Перейти в папку с проектом, установить виртуальное окружение и активировать его:
```
 python3 -m venv venv
 ```
 ```
 source venv/bin/activate
 ```
4. Создайте файл .env внутри папки <u>infra</u>, в котором укажите переменные окружения:
   * SECRET_KEY
   * DB_ENGINE
   * DB_NAME
   * POSTGRES_USER
   * POSTGRES_PASSWORD
   * DB_HOST
   * DB_PORT
   
5. Перейдите в папку **infra** командой:
 ```
 cd infra/
 ```
6. Запустите процесс сборки контейнера командой:
 ```
docker-compose up -d
 ```
7. Запустите миграции внутри контейнера командами:
```
docker-compose exec web python manage.py makemigrations
docker-compose exec web python manage.py migrate
```
8. Создайте супер пользователя командой:
```
docker-compose exec web python manage.py createsuperuser
```
9. Загрузите статику командой:
```
docekr-compose exec web python manage.py collectstatic --no-input
```
10. Для остановки работы контейнеров используйте команду:
```
docker-compose stop
```
11. Для пересборки контейнеров используйте команду:
```
docker-compose up -d --build
```
12. Для доступа в админку перейдите по ссылке:
```
http://localhost/admin/
```
13. Подробное описание отправки запросов и получения ответов на них можно посмотреть на странице:
```
http://localhost/redoc/
```

# Разработчик
Александр Королев
