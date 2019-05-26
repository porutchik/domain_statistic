# Статистика доменов
Скрипт для сбора статистики для зон ru/su/rf. Собираются все записи c DNS, 
Автономная система, переод делегирования

Статья с описанием https://habrahabr.ru/post/301894/

Для работы необходимы модули:
- MySQLdb
- dnspython
- SubnetTree
- psutil >= 2.2

Самый простой вариант запуска через Docker.

# Пример запуска:

устанавливаем Docker и git

* sudo apt-get update 
* sudo apt-get install docker.io git

Скачиваем репозиторий

* cd /home
* git clone https://github.com/porutchik/domain_statistic.git

Собираем образы

* cd domain_statistic/docker
* docker-compose build

запускаем контейнеры

* docker-compose up -d


Далее каждую ночь база данных доменов будет обновляться. На двух 
процессорах E5-2620v3 с 32 гигабайтами памяти процесс обновления БД з
анимает 11-12 часов, плюс еще несколько часов агрегирование данных.
