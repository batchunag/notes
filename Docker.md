#See CPU, Memory usage of containers
docker ps -q | xargs  docker stats --no-stream

#docker pause, unpause 
#docker ps, stop, start

#stop all containers:
docker kill $(docker ps -q)

#remove all containers
docker rm $(docker ps -a -q)

#remove all docker images
docker rmi $(docker images -q)

#Command line access to the container 
 enter-container image

#Show dangling images
docker images -f dangling=true 

#CLEAN UP space for docker, hobo
```bash
#!/bin/bash

# remove exited containers:
docker ps --filter status=dead --filter status=exited -aq | xargs -r docker rm -v
    
# remove unused images:
docker images --no-trunc | grep '<none>' | awk '{ print $3 }' | xargs -r docker rmi

# remove unused volumes:
find '/var/lib/docker/volumes/' -mindepth 1 -maxdepth 1 -type d | grep -vFf <(
  docker ps -aq | xargs docker inspect | jq -r '.[] | .Mounts | .[] | .Name | select(.)'
) | xargs -r rm -fr
```


#kill processes with specific names
dockeri rm $(docker ps |grep 'hobo' | awk '{print $1;}')

#Docker IP
docker inspect <container ID>

#Top-like interface for container metrics
ctop
https://github.com/bcicen/ctop

#cadvisor for status

#start docker


docker errors



#docker container log: Useful esp. when hobo is successful but you don't see the ip address
docker logs <containter-name>

#find container name
Run advanced docker ps, or run the docker command again.	