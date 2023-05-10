## docker 
 +  docker images ----- to show container images
 +  docker pull <image_name>  ----  pull container images
 +  docker ps ----   to show running conatiner 
 +  docker ps -a ---- to show all container 
 +  docker rmi <img_name /imgage_id> --- to remove container images
 +  docker run <image_name> ----  to run container
 +  docker stop <container_name/container_id>  --- to stop running container
 +  docker rm <container name>  ---  to remove container 
 + docker start <container name >  -- to start stop container
 + docker rm -f <container name >  --- to remove running container 
 +  docker commit <container_name>  <newImg_name>    -----  to create an image from container
 + docker exec -it <container name > <shell_name >  to get intraactive terminal
 + docker login ---- login cli in docker hub registry
 + docker logout --- logout cli in docker hub registry
 + docker attach <container name >  ---- to attach from main process
 + docker stats <container name >  ----  to check resources ocupied by container 
 + docker tag <old_img>  <new_IMGname>  ---- to change image name 
 + docker push <img_name >  ---- to push img in docker registry
 + docker inspect <container name > ---- to inspect details of conatiner
 + docker logs <container name>  ----- to see logs 
 + docker build -t <IMGname> <location_of_Dockerfile>  --- to build dockerImg
 ### if change name of dockerfile
 ```
 + docker build -t <IMGname> -f <chnage_name_of_dockerfile>  <Path>
 ```
 ## docker run options 
 + docker run 
 + --name <name_of_container>  
 + -p <port_to_access>:<port_of_service> 
 + -it -----  to get intrative terminal
 + -d ---- run in background
 ## docker volumes 
 ```
docker volume ls --- list of vol
docker volume inspect <volname>  -- details of vol
docker volume rm <Volname>   --- remove vol
docker volume prune --- remove all vol
dokcer volume create <volname>  -- create a volume

docker run -v volname:<mount _path>
docker run -v ./:<mount_path>
```
 
# history
```
docker run -d alpine ping google.com
 1708  docker ps
 1709  docker exec -it friendly_leavitt bash
 1710  docker exec -it friendly_leavitt sh
 1711  docker attach friendly_leavitt 
 1712  docker ps
 1713  docker p
 1714  docker ps
 1715  docker run -it ubuntu bash
 1716  docker ps
 1717  docker exec -it elastic_bartik bash
 1718  docker attach elastic_bartik 
 1719  docker inspect friendly_leavitt 
 1720  docker ps
 1721* 
 1722  docker attach elastic_bartik 
 1723  docker ps
 1724  docker commit elastic_bartik myfirstimg
 1725  docker images 
 1726  docker stop elastic_bartik 
 1727  docker os
 1728  docker ps
 1729  docker run -itd -p 1188:80 myfirstimg
 1730  docker ps
 1731  ifconfig 
 1732  rm .docker/config.json 
 1733  docker login
 1734  cat .docker/config.json 
 1735  docker images
 1736  docker tag myfirstimg
 1737  docker tag myfirstimg aakashgaur57/myfirstimg
 1738  docker images 
 1739  docker push aakashgaur57/myfirstimg
```
