# LNNDM
Набор и инструкция для установки ПО на VDS для работы с DOCKER.

Основное:
- NodeJS
- Docker
- DockerCompose
- Nginx
- MySql

Дополнительно:
- CertBot
- OpenSSL
# NodeJS
Статья для установки: https://losst.ru/ustanovka-node-js-ubuntu-18-04

ВАЖНО! Команда <source /etc/profile> не поможет Вам, просто перезапустите терминал.

ВАЖНО! Версию nvm выбирайте 16.14.2.
# Docker & docker-compose
Статья для установки docker: https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04-ru
Статья для установки docker-compose: https://docs.docker.com/compose/install/

ВАЖНО! Если пишет, что docker-compose не установлен при запуске, то выполните <sudo apt-get install docker-compose>
# Nginx
Статья для установки: https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04-ru
# MySql
Статья для установки: https://losst.ru/ustanovka-mysql-ubuntu-16-04

ВАЖНО! После установки НЕ ЗАПУСКАТЬ плагин mysql_secure, просто войди в mysql (<mysql -u root -p>), когда попросит пароль, просто нажми enter. Далее введи <ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password by 'ПАРОЛЬ';>
  
ВАЖНО! Далее, не выходя с терминала создай юзера - <CREATE USER 'ЮЗЕР'@'%' IDENTIFIED BY 'ПАРОЛЬ'>, дать ему все права - <GRANT ALL PRIVILEGES ON *.* TO 'ЮЗЕР'@'%' WITH GRANT OPTION>
  
ВАЖНО! Зайти в кфг mysql (/etc/mysql/my.cnf), и заменить bind-address = 127.0.0.1 на bind-address = 0.0.0.0, если ничего нет, то добавьте
  
[mysqld]
bind-address = 0.0.0.0

И перезапустите сервис (<sudo systemctl restart mysql>).
# CertBot и OpenSSL
Статья для установки certbot: https://habr.com/ru/post/318952/
  
ВАЖНО! При получении сертификата, при выборе webroot OR standalone, выбирать standalone (Цифра 1).
