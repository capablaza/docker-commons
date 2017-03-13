# docker-commons

#### Remove all images not used
docker images -a --no-trunc | grep 'none' | awk '{print $3}' | xargs docker rmi

#### Remove all containers not used
docker ps --filter status=dead --filter status=exited -qa | xargs docker rm -f 

#### Remove unused volumes:
docker volume ls -f dangling=true | awk '{ print $2 }' | xargs docker volume rm
