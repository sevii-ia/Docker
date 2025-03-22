# Docker

Цей репозиторій містить конфігураційні файли та налаштування для роботи з Docker.

## Вимоги

- Docker >= 20.x
- Docker Compose >= 2.x (за потреби)

## Структура репозиторію

```
Docker/
│── services/        # Налаштування окремих сервісів
│── configs/         # Конфігураційні файли
│── docker-compose.yml # Композиція контейнерів
│── Dockerfile       # Базовий образ
│── scripts/         # Скрипти для автоматизації
```

## Використання

1. Клонувати репозиторій:
   ```sh
   git clone https://github.com/sevii-ia/Docker.git
   cd Docker
   ```

2. Запустити сервіси через Docker Compose:
   ```sh
   docker-compose up -d
   ```

3. Переглянути запущені контейнери:
   ```sh
   docker ps
   ```

4. Остановити всі контейнери:
   ```sh
   docker-compose down
   
