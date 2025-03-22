# Docker Setup

Цей репозиторій містить скрипт для налаштування Docker на вашій системі. Ви можете використовувати ці інструкції для встановлення Docker на вашу машину.

## Встановлення

Щоб встановити Docker, виконайте наступні кроки:

1. Оновіть ваші пакети:
    ```bash
    sudo apt -y update
    ```

2. Встановіть Docker:
    ```bash
    sudo apt install -y docker.io
    ```

3. Запустіть Docker:
    ```bash
    sudo systemctl start docker
    ```

4. Увімкніть автоматичний запуск Docker при завантаженні системи:
    ```bash
    sudo systemctl enable docker
    ```

## Перевірка установки

Щоб перевірити, чи Docker був успішно встановлений, виконайте команду:
```bash
docker --version
