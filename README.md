## docker 
 +  docker images ----- to show container images
 +  docker pull <image_name>  ----  pull container images
 +  docker ps ----   to show running conatiner 
 +  docker ps -a ---- to show all container 
 +  docker rmi <img_name /imgage_id> --- to remove container images
 +  docker run <image_name> ----  to run container
 +  docker stop <container_name/container_id>  --- to stop running
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
 #### if change name of dockerfile
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
```
#### attach volume in container
```
docker run -v volname:<mount _path> <imgname>
docker run -v <absolute_path>:<mount_path> <imgname>
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
## docker network
 ### types of networks 
 + none
 + host
 + bridge
 
 ```
 docker network ls
 docker network create jecrc
 docker network inspect jecrc 
 docker network create jecrc2 --subnet 192.168.1.0/24
 docker network rm jecrc ---> to remove jecrc network
 docker network prune   -----> to remove all network apart from default
 

 ```
```
docker run -it --name c1 --network jecrc alpine sh
docker run -it --name c2 --network jecrc alpine sh
docker run -it --name c3 --network jecrc2 alpine sh
docker run -it --name c4 --network jecrc2 alpine sh
akash@sky:~$ docker network connect jecrc c3
akash@sky:~$ docker exec -it c3 sh
/ # ping c1
PING c1 (172.20.0.2): 56 data bytes
64 bytes from 172.20.0.2: seq=0 ttl=64 time=0.360 ms
64 bytes from 172.20.0.2: seq=1 ttl=64 time=0.204 ms
64 bytes from 172.20.0.2: seq=2 ttl=64 time=0.210 ms
^C
--- c1 ping statistics ---
3 packets transmitted, 3 packets received, 0% packet loss
round-trip min/avg/max = 0.204/0.258/0.360 ms
/ # ping c2
PING c2 (172.20.0.3): 56 data bytes
64 bytes from 172.20.0.3: seq=0 ttl=64 time=0.409 ms
64 bytes from 172.20.0.3: seq=1 ttl=64 time=0.230 ms
64 bytes from 172.20.0.3: seq=2 ttl=64 time=0.216 ms
^C
--- c2 ping statistics ---
3 packets transmitted, 3 packets received, 0% packet loss
round-trip min/avg/max = 0.216/0.285/0.409 ms

 ```
 ## docker portainer
 ```
 docker volume create portainer_data
 ```
 ```
 docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
 ```
 ### now open in web browser
 ```
 https://localhost:9443
 ```
