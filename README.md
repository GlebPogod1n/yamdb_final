![yamdb_final event parameter](https://github.com/GlebPogod1n/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg?event=push)

# Yamdb

### О проекте

API Yamdb - это бэкэнд часть аггрегатора отзывов на произведения различных категорий: книги, фильмы, музыка. Самих произведений на Yamdb нет, только отзывы с оценками. Пользователи могут просматривать рейтинг произведений в различных категориях и жанрах, читать отзывы к произведениям и оставлять свои комментарии к этим отзывам. Реализована кастомная модель юзер, есть разные роли пользователей - суперюзер, админ, модератор, юзер, аноним. Каждый пользователь обладает собственными правами на создание\удаление пользователей, произведений, отзывов и комментариев.

Это совместный проект и настоящая командная работа трёх студентов на Яндекс.Практикум, с применением Docker, Docker Compose и DockerHub.

### Настроен CI/CD

Запуск Flake8 и тестов, обновление образа DockerHub, деплой на сервер.

![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white)
 ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/github%20actions-%232671E5.svg?style=for-the-badge&logo=githubactions&logoColor=white) ![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![DjangoREST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=for-the-badge&logo=django&logoColor=white&color=ff1709&labelColor=gray) ![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white) 

### Как запустить проект:

Проект запускается на сервере с Ubuntu в контейнерах Docker

- Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/GlebPogod1n/yamdb_final.git
```
Выполните вход на свой удаленный сервер

Установите docker на сервер:

```
sudo apt install docker.io
```

Установите docker-compose на сервер:

```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```
cd infra_sp2
```

```
cd infra
```
- Запустить docker-compose

```
docker-compose up -d --build
```
Выполнить по почереди следующие команды:

```
docker-compose exec web python manage.py migrate
```
```
docker-compose exec web python3 manage.py createsuperuser
```
```
docker-compose exec web python3 manage.py collectstatic --no-input 
```
```
sudo docker-compose exec web python3 manage.py loaddata fixtures.json
```
```
### Заполнение базы данных тестовыми данными:
```
Из корневой папки проекта перейти в папку api_yamdb:

```
cd api_yamdb
```
Заполнить базу данными из csv файлов:

```
python manage.py fill_db
```
```
### Проект будет доступен локально по адресу:
```
```
http://localhost/
```
```
### Примеры обращений к API Yatube:
```
По адресу http://127.0.0.1:8000/redoc/ подключена документация, в которой
описаны все примеры обращений к API
```
### Авторы:

Погодин Глеб - [https://github.com/GlebPogod1n](https://github.com/GlebPogod1n)     
Трофимов Руслан - [https://github.com/EdmondKoko](https://github.com/EdmondKoko)   
Чабанный Денис - [https://github.com/DociDog](https://github.com/DociD)
```
```
### контейнеризация, CI/CD:

Погодин Глеб - [https://github.com/GlebPogod1n](https://github.com/GlebPogod1n)
```