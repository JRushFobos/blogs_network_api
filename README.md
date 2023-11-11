# blogs_network_api
API для размешения блогов. Позволяет удаленно управлять публикациями и комментариями, создавать подписки.

### Стек технологий
API написан на Django+DRF c библиотеками djoser и djangorestframework-simplejwt для работы JWT-токенов.

### Шаги для запуска проекта
1. Клонируйте репозиторий и перейдите в него в командной строке:
    ```bash
    git clone https://github.com/JRushFobos/blogs_network_api.git
    cd blogs_network_api
    ```

2. Перейти в папку репозитория:
    ```bash
    cd blogs_network_api
    ```

3. Cоздайте и активируйте виртуальное окружение:
    ```bash
    # Для Linux/macOS:
    python3 -m venv venv
    source venv/bin/activate
    # Для Windows:
    python -m venv venv
    source venv/Scripts/activate
    ```

4. Установите зависимости из файла requirements.txt:
    ```bash
    python3 -m pip install --upgrade pip
    pip install -r requirements.txt
    ```

5. Выполните миграции и запустите проект:
    ```bash
    python3 manage.py migrate
    python3 manage.py runserver
    ```

### Примеры запросов
- Подробная документация API: `/redoc/` (GET)
- Получить JWT-токен: `api/v1/jwt/create/` (POST)
    ```json
    {
        "username": "string",
        "password": "string"
    }
    ```
- Получить список всех публикаций: `/api/v1/posts/` (GET)
- Создать новую публикацию: `/api/v1/posts/` (POST)
    ```json
    {
        "text": "Новый пост",
        "image": "data:image/png;base64,<...>",
        "group": 1
    }
    ```
- Удалить комментарий к публикации: `/api/v1/posts/{post_id}/comments/{id}/` (DELETE)
- Получить информацию о сообществе: `/api/v1/groups/{id}/` (GET)
- Подписаться на пользователя: `/api/v1/follow/` (POST)
    ```json
    {
        "following": "username"
    }
    ```

### Об авторе
Мокрушин Евгений [@JRushFobos](https://github.com/JRushFobos)
