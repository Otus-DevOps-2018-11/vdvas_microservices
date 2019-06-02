# vdvas_microservices
# Homework №15  
Monitoring-1.  
Запустим готовый образ prometheus.  
Ознакомимся с вэб интерфейсом prometheus.  
Переупорядочим структуру репозитория.  
Сбилдим образ prometheus, использую заготовленный prometheus.yml.  
Сбмлдим образы нашего приложения.  
Перепишем docker-compose.yml используя образы наших приложений и добавим сервис prometheus.  
Запуск docker-compose с .env файлом  
`sudo env $(cat .env) docker-compose up -d`  
Это специфика версии docker-compose 1.24.0  
Проверим healthcheck's работающих сервисов в prometheus.  
Добавим сервис node_exporter в docker-compose.  
Добавим описание в prometheus.yml и пересоберем контейнер prometheus.  
Пересоздадим сервисы в docker-compose.  
Проверим нагрузку cpu на хосте в prometheus.  
Ссылка на докер хаб  
https://hub.docker.com/?namespace=vdvas  

# Homework №14  
Docker-4  
Исследуем контейнеры с 3 видами сетей:  
- none  
- host network  
- brigde  
Запустим наше приложение, подключив контейнеры к bridge сети.  
Остановим контейнеры и запустим, указав сетевые алиасы.  
Создадим 2 новых brigde сети с разными подсетями.  
Запустим наши контейнеры подключив часть контейнеров к одной, а часть к другой сети.  
Установим docker compose и напишем конфиг.  
Параметризируем конфиг, опишем параметры в файл .env.  
Имя проекта определяется переменной COMPOSE_PROJECT_NAME в файле .env.  

# Homework №13  
Docker-3  

Скачаем архив с приложением, которое состоит из 3 компонент. Каждый компонент находится в отдельной папке.  
Создадим для каждого  омпонента свои Dockerfile.  
Соберем докер образы для компонентов.  
Создадим bridge сеть и запустим контейнеры.  
Уменьшим размер образа ui поменял Dockerfile и пересоберем образ.  
Перезапустим наши контейнеры. Убедимся что приложение работает.  
Вынесем базу данных в volume, изменив команду запуска контейнера.

# Homework №12  
Docker-2  
Запустим докер хост и повторим практику из лекции по изучению:  
• PID namespace (изоляция процессов)  
• net namespace (изоляция сети)  
• user namespaces (изоляция пользователей)   
Создадим Dockerfile в котором уакжем какие пакеты установить и скопируем заранее приготовленные файлы конфигов mongodb.conf.  
Соберем образ командой docker build.  Откроем порт в фаерволе.  
Запустим контейнер командой docker run и проверим что приложение работает http://ip:9292.  
Запушим получившийся образ в Docker Hub и запустим образ из докер хаба на другой машине.


# Homework №11  
Docker-1  
vdvas microservices repository<br>
Был установлен docker по мануалу https://docs.docker.com/install/linux/docker-ce/ubuntu/ на ВМ в GCP <br>
Был запущен первый контейнер hello-world <br>
```
docker run hello-world <br>
```
Были изучены команды работы с контейнерами и образами<br>
```
docker ps 
docker images
```
Был запущен новый контейнер и подключена консоль к новому контейнеру<br>
```
docker run -it ubuntu:16.04 /bin/bash 
```
Ручной запуск и подключение к терминалу определенного контейнера<br>
```
docker start <u_container_id>
docker attach <u_container_id>
```
Запущен контейнер в background режиме<br>
```
docker run -dt nginx:latest
```
Запуск команды в контейнере<br>
```
docker exec -it <u_container_id> bash
```
Создали коммит из контейнера<br>
```
docker commit <u_container_id> yourname/ubuntu-tmp-file 
```
Сравнение вывода команд<br>
```
docker inspect <u_container_id>
docker inspect <u_image_id>
```
ПОнимание разницы между контейнером и образом.<br>
Заполнение файла docker-monolith/docker-1.log<br>
Завершение работы контейнера<br>
```
docker kill $(docker ps -q) 
```
Удаление контейнеров<br>
```
docker rm $(docker ps -a -q)
```
Удаление образов<br>
```
docker rmi $(docker images -q) 
```
