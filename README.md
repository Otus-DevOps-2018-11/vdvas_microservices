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
Запуск команды в контейнере
docker exec -it <u_container_id> bash
Создали коммит из контейнера
docker commit <u_container_id> yourname/ubuntu-tmp-file 
Сравнение вывода команд
>docker inspect <u_container_id>
>docker inspect <u_image_id>
ПОнимание разницы между контейнером и образом.
Заполнение файла dockermonolith/docker-1.log
Завершение работы контейнера
docker kill $(docker ps -q) 
Удаление контейнеров
>docker rm $(docker ps -a -q)
Удаление образов
docker rmi $(docker images -q) 
