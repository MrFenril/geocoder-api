docker build -f ./Dockerfile -t yolo/addok:latest .
docker service logs geocoder_addok-fr -f => link to container
docker service ps geocoder_addok-fr --no-trunc => show services
docker stack deploy -c ./docker/docker-compose.yml geocoder => deploy image
docker stop $(docker ps -q -f name=geocoder_addok-fr.1) && docker rm $(docker ps -q -f name=geocoder_addok-fr.1)
docker stack rm geocoder
