### Описание проекта:

Социальная сеть авторов, где пользователи могут оставлять посты и комментарии к постам других пользователей, а также подписываться друг на друга. Здесь царит мир и любовь - за войну в комментах наказывают принудительным просмотром котиков в течение одного часа.

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone git@github.com:crazyLixxx/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source env/bin/activate
```

Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

### Примеры запросов к api:

Список постов
Запрос:
/api/v1/posts/
Ответ:
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}

Конкретный пост
Запрос:
/api/v1/posts/{id}/
Ответ:
{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2019-08-24T14:15:22Z",
  "image": "string",
  "group": 0
}

Оставить комментарий
Запрос:
/api/v1/posts/{post_id}/comments/
Ответ:
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}

Более подробное описание api можно найти в документации:
http://127.0.0.1:8000/redoc/