# Тестовое задание медузы (deployment)

## Настройки по умолчанию

После запуска интерфейс доступен на порту 4001, простой тестовый клиент — на порту 4002, API - на порту 4000.
Интерфейс и клиент обращаются к API по адресу "http://localhost:4000".

## Первый запуск

```bash
docker-compose up -d db
docker-compose run --rm backend rake db:setup
docker-compose up -d 
```

## Миграция БД

```bash
docker-compose run --rm backend rake db:migrate
```

## Обычный запуск

```bash 
docker-compose up -d
```

## Смена адреса API сервера

Для смены адреса API, по которому обращается интерфейс и тестовый клиент необходимо установить переменную окружения `HOST`:

```bash
HOST=example.org docker-compose up -d
```

При такой настройке API запросы будут производиться по адресу "http://example.org:4000".
