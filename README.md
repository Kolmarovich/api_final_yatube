### Описание проекта:

Проект api_yatube - это API социальной сети yatube.

С помощью api_yatube можно запрашивать данные о постах, группах, комментариях в социальной сети Yatube, а также создавать новые.

Yatube - это учебный проект курса "backend-python" от Яндекс-Практикума.

Автор: Берников Николай

### Технологии:
- Python 3.9
- djangorestframework 3.12.4
- djoser 2.1.0

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone git@github.com:Kolmarovich/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv venv
```

```
source venv/bin/activate
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

### Примеры запросов к API:

Получить список всех постов (GET):
```
http://127.0.0.1:8000/api/v1/posts/
```
Пример ответа:
```
{
    "count": 123,
    "next": "http://api.example.org/accounts/?offset=400&limit=100",
    "previous": "http://api.example.org/accounts/?offset=200&limit=100",
    "results": [
        {}
    ]
}
```

Получить определенный пост (GET):
```
http://127.0.0.1:8000/api/v1/posts/1/
```
Пример ответа:
```
{
    "id": 1,
    "author": "string",
    "text": "string",
    "pub_date": "2023-10-08T13:53:18.915118Z",
    "image": null,
    "group": 1
}
```

Получить коментарии определенного поста (GET):
```
http://127.0.0.1:8000/api/v1/posts/1/comments/
```
Пример ответа:
```
[
    {
        "id": 0,
        "author": "string",
        "text": "string",
        "created": "2019-08-24T14:15:22Z",
        "post": 0
   }
]
```

Получить список всех групп (GET):
```
http://127.0.0.1:8000/api/v1/groups/
```
Пример ответа:
```
[
    {
        "id": 0,
        "title": "string",
        "slug": "string",
        "description": "string"
    }
]
```

Создать новый пост (POST):

(Требуется аутентификация)
```
http://127.0.0.1:8000/api/v1/posts/
```
Пример ответа:
```
{
    "text": "string",
    "image": "string",
    "group": 0
}
```
