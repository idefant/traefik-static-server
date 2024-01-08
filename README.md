# traefik-static-server

Контейнер для шаринга статических файлов. Не требуется перезапуск после обновления содержимого папки `shared`.

## Продакшн

1. [Запуск Traefik](./how-to-start-traefik.md)
2. Настроит ь `.env` под себя
3. Заменить файлы в папке `shared`
4. Запустить контейнер с помощью одной из двух команд:
  - для http: `docker compose -f docker-compose.http.yml up -d`
  - для https: `docker compose -f docker-compose.https.yml up -d`
