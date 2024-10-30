## Hello DevOps Rosatom

# Сборка и запуск

Запуск текущего docker-compose с logrotate:
```
cd example
docker compose up -d
```

```
http://localhost:80
```

## Ссылка на образ в Docker Hub
```
https://hub.docker.com/repository/docker/studentq1/rosatom/
```

### Работа с docker image
Запуск контейнера:
```
docker run -d -p 80:80 studentq1/rosatom
```

Сборка с docker-compose.yml:
```
version: '3'
services:
  nginx:
    container_name: nginx
    image: studentq1/rosatom:latest
    ports:
      - 80:80
    restart: always
```

### Настройка GITLAB CI

Переменные окружения:

CI_REGISTRY - docker.io
CI_REGISTRY_IMAGE - index.docker.io/studentq1/rosatom
CI_REGISTRY_USER, CI_REGISTRY_PASSWORD - логин и пароль docker.

