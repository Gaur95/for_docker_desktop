# for_docker_desktop
## download docker desktop
https://www.docker.com/products/docker-desktop 

## enable wsl 
https://learn.microsoft.com/en-us/windows/wsl/install-manual
## or  copy below command and run from cmd (run as administrator)
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
### now update wsl --- install and run it. ->>>

https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi

### then install docker desktop
### and check from cmd 
```
docker --version
```
# Projects 
## P-1
<img src=project1.png>

## P-2
<img src=project2.png>
