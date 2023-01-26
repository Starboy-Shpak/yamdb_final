# YAMDB_FINAL (Версия с CI/CD проекта)
https://github.com/Starboy-Shpak/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg

REST API проект для сервиса YAMDB — платформа для сбора отзывов о фильмах, книгах, музыке и чего угодно еще.

## Что проект умеет?

YAMDB собирает отзывы пользователей на произведения. Произведения делятся на категории: «Книги», «Фильмы», «Музыка» и т.д. Список категорий можно расширить.

### Технологии
Python, DRF, JWT

### Как запустить проект:
- Клонировать репозиторий и перейти в него в командной строке:
```
git clone git@github.com:Starboy-Shpak/api_yamdb.git
cd api_yamdb/
``` 
- Cоздать и активировать виртуальное окружение:
```
python -m venv env
source env/Scripts/activate
``` 
- Установить зависимости из файла requirements.txt:
```
python -m pip install --upgrade pip
pip install -r requirements.txt
``` 
- Перейти в каталог и выполнить миграции:
```
cd api_yamdb/
python manage.py migrate
``` 
- Запустить проект:
```