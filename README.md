# Lenta

**Краткое описание:**
Необходимо создать алгоритм прогноза спроса на 14 дней для товаров собственного
производства. Гранулярность ТК-SKU-День.

**Задача:**
Построить модель прогноза спроса на основе мастер данных и данных продаж с учетом разных
признаков.

**Цель:**
Сгенерировать различные признаки и придумать интерпретируемую, описывающую правильные
зависимости (повышение цены вызывает логичное падение спроса), модель прогноза спроса.
Дальше необходимо сделать подневной прогноз спроса на тестовом периоде для каждого товара
и магазина, и команда Ленты оценит его качество в сравнении с свершившимся фактом.
Метрикой качества будет выступать WAPE, посчитанный на уровне товар, магазин, день. Если
есть пропущенные значения и по каким-то товарам не предоставлен прогноз, прогноз считается
равным нулю.

### Установка:
Клонировать репозиторий и перейти в него в командной строке:
```
git clone https://github.com/Danspers/Lenta-time-series.git
```
```
cd Lenta-time-series
```
Клонировать и установить виртуальное окружение:

- для MacOS
```
python3 -m venv venv
source venv/bin/activate
```
- для Windows
```
python -m venv venv
source venv/Scripts/activate
```
Установить зависимости:

```
cd backend
```
```
pip install -r requirements.txt
```

В папке с файлом manage.py применить миграции:
```
python manage.py makemigrations
```
```
python manage.py migrate
```
Создание админа:
```
python manage.py createsuperuser
```

Выполните команду для запуска локально:

```
python manage.py runserver
```
Запуск тестов:

```
python manage.py test
```

Запустить все контейнера командой:

```
docker-compose up -d --build
```

Выполнить миграции:

``` 
docker-compose exec backend python manage.py migrate 
```

Создайте суперпользователя:
```
docker-compose exec backend python manage.py createsuperuser
```

Остановить работу всех контейнеров командой:
```
docker-compose down
```
Остановить работу:
```
docker-compose down
```
### Документация проекта:
После локального запуска проекта ( python manage.py runserver ), для просмотра документации - 

http://127.0.0.1:8000/swagger/

### Примеры запросов:

- http://127.0.0.1:8000/api/forecast/ - прогнозы

- http://127.0.0.1:8000/api/shops/ - магазины

- http://127.0.0.1:8000/api/sales/ - товары

- http://127.0.0.1:8000/api/categories/ - категории товаров

### Использумые технологии:

- Python - https://www.python.org/
- Django - https://www.djangoproject.com/
- Django Rest Framework - https://www.django-rest-framework.org/
- Docker - https://www.docker.com/
- Rest API - https://www.django-rest-framework.org/topics/documenting-your-api/
- PostgreSQL - https://www.postgresql.org/

## Авторы проекта
> Фронтенд-разработчики

- [Елизавета Циприс](https://github.com/dumisel)
- [Дарья Лазарчук](https://github.com/dashalalala24)

> Бэкэнд-разработчики

- [Иван Матвеев](https://github.com/Ivanmatv)
- [Мария Старикова ](https://github.com/Ivanmatv)

> Дата-аналитики

- [Артем Скребцов](https://github.com/Skrebcov)
- [Данила Солтык](https://github.com/Danspers)
- [Наталья Щеглова](https://github.com/NataliaShcheglova)

> Дизайнеры

- Кира Байгулова
- Елизавета Пикина
- Илья Болонин

> Проджект-менеджер

- Анастасия Баталова
