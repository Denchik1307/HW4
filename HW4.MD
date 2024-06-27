Задание 1:
1) Создаем docker-compose.yml файл для сервиса, состоящего из двух контейнеров:

```yaml
version: '3'
services:
  web:
    image: nginx:latest
  db:
    image: mysql:latest
    environment:
      MYSQL_ROOT_PASSWORD: example
```

2) Создаем 3 файлов docker-compose.dev.yml, docker-compose.prod.yml, docker-compose.lab.yml для каждого окружения:

docker-compose.dev.yml:
```yaml
version: '3'
services:
  web:
    image: nginx:latest
  db:
    image: mysql:latest
    environment:
      MYSQL_ROOT_PASSWORD: example
```

docker-compose.prod.yml:
```yaml
version: '3'
services:
  web:
    image: nginx:latest
  db:
    image: mysql:latest
    environment:
      MYSQL_ROOT_PASSWORD: example
```

docker-compose.lab.yml:
```yaml
version: '3'
services:
  web:
    image: nginx:latest
  db:
    image: mysql:latest
    environment:
      MYSQL_ROOT_PASSWORD: example
```

3) Запускаем сервисы на каждой ноде с использованием docker-compose up -d команды для каждого окружения.

4) На каждой ноде должно быть по 2 работающих контейнера, по одному для каждого сервиса (web и db). Проверяем с помощью docker ps -a на каждой ноде, что контейнеры работают.

Задание 2:
1) Создаем два файлa: docker-compose.lab.yml и docker-compose.dev.yml, где будут описаны сервисы для лаборатории и разработки соответственно.

docker-compose.lab.yml:
```yaml
version: '3'
services:
  web:
    image: nginx:latest
  db:
    image: mysql:latest
    environment:
      MYSQL_ROOT_PASSWORD: example
```

docker-compose.dev.yml:
```yaml
version: '3'
services:
  web:
    image: nginx:latest
  db:
    image: mysql:latest
    environment:
      MYSQL_ROOT_PASSWORD: example
```

2) Запускаем сервисы на каждой ноде с использованием docker-compose -f docker-compose.lab.yml up -d и docker-compose -f docker-compose.dev.yml up -d команд для каждого окружения.

3) Проверяем, что на каждой ноде корректно запустились по 2 контейнера для каждого сервиса.

После завершения заданий, результаты проверяем с помощью команды docker ps -a и удостоверяемся, что на каждой ноде содержится по 2 работающих контейнера для каждого сервиса.
