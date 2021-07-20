# Проект YATUBE
Социальная сеть
### Описание
Благодаря этому проекту можно выбирать тематику и создавать посты, оставлять комментарии под постами и подписываться на любимых авторов.
### Технологии
Python, Django, DRF, DRF-simplejwt
### Запуск проекта в dev-режиме
- Клонировать репозиторий и перейти в него в командной строке:
- Установите и активируйте виртуальное окружение:
**Для пользователей Windows**
```
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
Запуск проекта:
```
python manage.py runserver
```
### Авторы
GerG
