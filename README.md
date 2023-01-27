# YAMDB_FINAL (Версия с CI/CD проекта)
![yamdb_workflow](https://github.com/Starboy-Shpak/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

REST API проект для сервиса YAMDB — платформа для сбора отзывов о фильмах, книгах, музыке и чего угодно еще.

## Что проект умеет?

YAMDB собирает отзывы пользователей на произведения. Произведения делятся на категории: «Книги», «Фильмы», «Музыка» и т.д. Список категорий можно расширить.

### Как запустить проект:

Клонируем репозиторий и переходим в него:

```
git clone git@github.com:Starboy-Shpak/yamdb_final.git
cd yamdb_final
```
Переходим в папку с файлом docker-compose.yaml:
```
cd infra
```
Создаем в директории /infra файл  `.env`  с переменными окружения:
```
SECRET_KEY=<key>               # стандартный ключ, который создается при старте проекта

DB_NAME=postgres               # имя БД
POSTGRES_USER=postgres         # логин для подключения к БД
POSTGRES_PASSWORD=<password>   # пароль для подключения к БД (установите свой)
DB_HOST=db                     # название сервиса (контейнера)
DB_PORT=5432                   # порт для подключения к БД
```
Далее запускаем Docker Compose:
```
docker compose up -d --build
```
Выполняем миграции:
```
docker compose exec web python manage.py migrate
```
Создаем суперпользователя:
```
docker compose exec web python manage.py createsuperuser
```
Собираем статику:
```
docker compose exec web python manage.py collectstatic --no-input
```
Создаем дамп базы данных (нет в текущем репозитории):
```
docker compose exec web python manage.py dumpdata > dumpPostrgeSQL.json
```

Админка проекта доступна по: [ссылке](http://51.250.18.184/admin/)

***
Автор: Вадим Шпак.
Связаться со мной можно в [телеграм](https://t.me/starboy_shpak/)
