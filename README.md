Описание

Проект представляет собой API для yatube.

Ключевые моменты:

Применены вьюсеты.

Для аутентификации использованы JWT-токены.

У неаутентифицированных пользователей есть доступ к API только для чтения. Исключение — эндпоинт /follow/, доступ к нему предоставляется только аутентифицированным пользователям. 

Аутентифицированным пользователям разрешено изменение и удаление своего контента; в остальных случаях доступ предоставляется только для чтения.

Установка

1) Склонировать репозиторий:
Клонировать репозиторий (git clone) и перейти в него в командной строке (cd)

2) Создать и активировать виртуальное окружение для проекта

PY -m venv venv

source venv/scripts/activate

3) Установить зависимости из файла requirements.txt:
PY -m pip install --upgrade pip

PY pip install -r requirements.txt

4) Сделать миграции
PY manage.py makemigrations

PY manage.py migrate

5) Запустить сервер
PY manage.py runserver

Примеры

Для доступа к API необходимо получить JWT-токен: выполнить POST-запрос localhost:8000/api/v1/token/, передав поля username и password.

При дальнейшей отправке запросов токен передается в заголовке Authorization: Bearer <токен>

Примеры обращения к методам:

/api/v1/posts/ (GET, POST, PUT, PATCH, DELETE)

api/v1/posts/{post_id}/comments/ (GET, POST, PUT, PATCH, DELETE)

/api/v1/follow/ (GET, POST)

/api/v1/groups/ (GET)