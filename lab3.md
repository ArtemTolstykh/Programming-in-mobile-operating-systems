Остановка всех контейнеров
docker stop $(docker ps -a -q)

Удаление всех контейнеров:
docker container rm $(docker ps -a -q)

Удаление всех образов:
docker image prune -a

Удаление всех дисков:
docker volume rm $(docker volume ls -q)

Удаление всех остановленных контейнеров и неиспользуемых образов:
docker system prune -a

Установка Docker Registry:
docker run -d --name registry-ui -p 8080:80 jc21/registry-ui

Установка Shipyard и подключение к API docker:
docker run -d --name shipyard --link registry-ui:registry-ui -v /var/run/docker.sock:/var/run/docker.sock shipyard/shipyard

Установка лимита на контейнер apache:
docker run -d --name=apache -m 128m -p 80:80 httpd:latest