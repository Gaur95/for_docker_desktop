# jenkins
```
docker run -itd -v v1:/var/jenkins_home -v /run/docker.sock:/run/docker.sock -v /usr/bin/docker:/bin/docker  -p 8080:8080 -p 50000:50000 jenkins/jenkins 
```
