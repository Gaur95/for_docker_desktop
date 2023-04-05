# for_docker_desktop

https://www.docker.com/products/docker-desktop 

https://learn.microsoft.com/en-us/windows/wsl/install-manual

# SHELL
<img src='shell.jpg'>

## types of shell
<img src='shelltype.png'>

## cmd
### chsh  --- to use change shell 
<img src='cmd.png'>

### cat /etc/shell      ---- to show all available shell
### echo $PATH          ----- instructs a Linux system in which directories to search for executables
### passwd              ----- to change user's password



# User managment 
<img src='user.png'>

### loaction of user's details 

```
cat /etc/passwd 
```
<img src='userdetails.png'>

### Add User
adduser <username>
```
adduser hum
```
### Delete User
userdel <username> 

userdel -r <username>   ------------ also remove home directory of user
```
userdel -r hum
```

# group

<img src='group.png'>

## types of groups
<img src='typeofgroup.png'>

## group details 
```
cat /etc/group
```
<img src='groupdetails.png'>

### for adding user in group

<img src='usermode.png'>
<img src='usermode2.png'>

