# Проект YATUBE
Социальная сеть
### Описание
Благодаря этому проекту можно создавать посты, оставлять комментарии под постами и подписываться на понравившихся авторов.
### Технологии
Python, Django, DRF, DRF-simplejwt
### Запуск проекта в dev-режиме
- Клонировать репозиторий и перейти в него в командной строке:
- Установите и активируйте виртуальное окружение:
```
Для пользователей Windows:
python -m venv venv
source venv/Scripts/activate
python -m pip install --upgrade pip
```
- Установите зависимости из файла requirements.txt
```
pip install -r requirements.txt
```
- Перейдите в каталог с файлом manage.py выполните команды:
Выполнить миграции:
```
python manage.py migrate
```
Создайте супер-пользователя:
```
python manage.py createsuperuser
```
Запуск проекта:
```
python manage.py runserver
```
### Примеры
По умолчанию для неавторизованных пользователей проект доступен только для чтения.
```
api/v1/posts/ - получение списка всех постов
api/v1/posts/{id}/ - получение поста
api/v1/groups/ - получение списка всех групп
api/v1/groups/{id}/ - получение группы
api/v1/{post_id}/comments/ - получение списка всех комментариев под определенным постом
api/v1/{post_id}/comments/{id}/ - получение комментария
```
За исключением эндпоинта **follow** доступен только авторизованных пользователей.
```
api/v1/follow/ - получение подписок текущего пользователя
api/v1/follow/{id}/ - получение одной подписки
```
И **users** доступен только для админа:
```
api/v1/users/ - получение списка пользователей
api/v1/users/{id}/ - получение пользователя
```
- Авторизованные пользователи могут создавать посты, комментировать их и подписываться на других пользователей.
- Пользователи могут изменять(удалять) контент, автором которого они являются.
Так же в проекте присутсвует пагинация(LimitOffsetPagination), поиск и сортировка, примеры ниже
```
api/v1/posts/?limit=10&offset=0 - Пагинация на 10 постов, начиная с первого
api/v1/posts/?search=your_search - Поиск в тексте, постов пользователя, группы
api/v1/posts/?ordering=-pub_date - сортировка по дате создания постов(сначало новые)
```

### Добавление сообществ проект реализованного через админ панель Django:
```
admin/ - после авторазиации, перейдите в раздел "сообщества" и создайте тематики
```
Доступ авторизованным пользователем доступен по jwt-токену, который можно получить выполнив POST запрос по адресу:
```
api/v1/jwt/create/
```
Передав в body данные пользователя:
```
{
"username": "your_nickname",
"password": "your_password"
}
```
Получив токен его нужно добавить в headers, после этого вам буду доступны все функции проекта:
```
Authorization: Bearer {your_token}
```
Проверить и обновить токен можно по следующием эндпоинтам:
```
api/v1/jwt/refresh/ - Обновление токена
api/v1/jwt/verify/ - Проверка токена
```

### Авторы
GerG
