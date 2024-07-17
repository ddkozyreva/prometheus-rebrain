# prometheus-rebrain

## PROM FINAL: Финальное задание
Описание:
В итоговом задании вам предстоит настроить мониторинг нескольких серверов с помощью prometheus. Вам будет выдано две ноды - node1 и prometheus, на которые вам предстоит установить некоторые сервисы и подключить их мониторингу prometheus.

Итак, что требуется сделать:

На node1:
1.1. Установить docker по официальному мануалу

1.2. Установить docker-compose по приведенному решению

1.3. Запуск "wordpress" через docker-compose.yml:

Создайте папку db_data в домашней директории.
Создайте папку wordpress_data в домашней директории.
сконфигурируйте для wordpress docker-compose файл следующим образом:

```
version: "3.8"

services:
  db:
    image: mysql:5.7
    volumes:
      - db_data:/var/lib/mysql
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: YOUR_ROOT_DB_PASSWORD
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wordpress
      MYSQL_PASSWORD: YOUR_DB_PASSWORD

  wordpress:
    depends_on:
      - db
    image: wordpress:latest
    volumes:
      - wordpress_data:/var/www/html
    ports:
      - "8000:80"
    restart: always
    environment:
      WORDPRESS_DB_HOST: db:3306
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: YOUR_DB_PASSWORD
      WORDPRESS_DB_NAME: wordpress

volumes:
  db_data: {}
  wordpress_data: {}
```


1.4. Установить cadvisor для мониторинга docker.

1.5. Установить и запустить mysqld_exporter для мониторинга базы mysql.

1.6. Установить и запустить node_expoter для мониторинга состояния ноды.

На prometheus:
2.1. Запустить prometheus (можно в докере, можно через systemd)

2.2. Настроить сбор метрик с экспортеров, запущенных на node1 - cadvisor, mysqld_exporter, node_exporter.

2.3. Установить grafana и подключить к ней datasource prometheus.

2.4. Найти и импортировать dashboards из grafana.com для cadvisor, mysqld и node экспортеров.

После настройки необходимо сохранить конфигурацию prometheus.yml, логи запуска экспортеров - cadvisor, mysqld, node, а так же скриншоты каждого из dashboards в grafana - для cadvisor, mysqld и node_exporter. Все сохраненные файлы отправить на проверку куратору (предварительно залив на какой-нибудь файлообменник или в гит репозиторий).

```
Infrastructure:
node1: public ip: 159.223.6.112, login: user
prometheus: public ip: 165.232.85.92, login: user
```
