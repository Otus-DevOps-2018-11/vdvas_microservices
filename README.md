# vdvas_microservices
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
