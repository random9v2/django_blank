# Django-PostgreSQL-Angular framework in Docker
## Build and run
```
docker compose build
docker compose run --rm app

# Or for starting a new Django project...
docker compose run --rm app django-admin startproject core .
```
## Run and start application stack
```
docker compose up
```
## Run command in alpine container with sh; open shell
```
docker exec -it django_app sh
python manage.py shell
```
## Create new app
```
python manage.py startapp newapp
```