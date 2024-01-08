# Запуск Traefik в Docker

Traefik - Обратный прокси-сервер, написанный на Golang.

Если Traefik еще не запущен на сервере, то можно воспользоваться готовой конфигурацией в папке `traefik`. Если Traefik уже был настроен, то необходимо адаптировать конфигурацию (labels) в файлах `docker-compose.http.yml` и `docker-compose.https.yml`.

## Traefik еще не запущен

1. Добавим авторизацию, создав мидлварю `traefik-auth` и сгенерируем строку с логином и паролем (замечу, что каждый знак `$` нужно заменить на `$$`):

```sh
$ htpasswd -nb admin password
# admin:$apr1$vDSqkf.v$GTJOtsd9CBiAFFnHTI2Ds1
```

2. Полученную строку вставить вместо шаблонной в файле `traefik/docker-compose.yml`
3. Заменить домен на дашборд Traefik в `traefik/docker-compose.yml` на свой, заменить почту на свою в файле `traefik/traefik.yaml` для получения уведомлений от Let's Encrypt
4. Запуск контейнера с Traefik:

```sh
cd traefik
docker compose up -d
```

После этих действий дашборд Traefik должен быть доступен по домену.