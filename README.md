# docker-commons

#### Remove all images not used
docker images -a --no-trunc | grep 'none' | awk '{print $3}' | xargs docker rmi

#### Remove all containers not used
docker ps --filter status=dead --filter status=exited -qa | xargs docker rm -f 

#### Remove unused volumes
docker volume ls -f dangling=true | awk '{ print $2 }' | xargs docker volume rm

#### List all networks
docker network ls

#### List all volumes
docker volume ls

#### Docker images commands
docker images -a

docker rmi [replace_with_image_name]


#### Docker containers commands
docker ps -a

docker rm [replace_with_container_name]

docker start [replace_with_container_name]

docker stop [replace_with_container_name]