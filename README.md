## Описание:

API для Yatube это проект, в котором пользователи могут публиковать записи, комментировать записи 
и подписываться на любимых авторов.


## Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://git@github.com:Grandkol/api_final_yatube.git
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
## Примеры запросов.

```
GET api/v1/posts/ - Получить список всех публикаций.

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
```
```
POST api/v1/posts/ - Добавление новой публикации в коллекцию публикаций.

{
  "text": "string",
  "image": "string",
  "group": 0
}
```

```
GET api/v1/posts/{id}/ - Получение публикации по id.

{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2019-08-24T14:15:22Z",
  "image": "string",
  "group": 0
}
```

```
PUT api/v1/posts/{id}/ - Обновление публикации по id. 

{
  "text": "string",
  "image": "string",
  "group": 0
}

```


```
PATCH api/v1/posts/{id}/ - Частичное обновление публикации по id.

{
  "text": "string",
  "image": "string",
  "group": 0
}
```

```
DELETE api/v1/posts/{id}/ - Удаление публикации по id. Удалить публикацию может только автор публикации. 
Анонимные запросы запрещены.

{
  "detail": "Учетные данные не были предоставлены."
}
```