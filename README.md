# Ansible
```
> 
> 
>   Ansible Machine -- (generally Linux machine only)
> 
> 
>    Ansible []  --------(key based ssh )-----------> server1 , server2
> 
> 
>    store room , warehouse , inventory 
> 
>  ansible --uses inventory file to maintain its target server to automation
> 
>  Module in ansible 
>   i) ping -- to test connection b/w ansible and target host 
> 
>   ii)  command 
> 
> --- when we have many modules to run -- its not a good idea to run it on 
>    command line 
> so we have to put them in a file --using YAML lang { playbook }
> 
> ansible adhoc commands 
```
# history
```
    1  sudo -i
    2  whoami
    3  ssh-keygen -t rsa
    4  ssh-copy-id ec2-user@172.31.7.10
    5  ssh-copy-id ec2-user@172.31.15.121
    6  history 
    7  ssh ec2-user@172.31.7.10
    8  ssh ec2-user@172.31.15.121
    9  history 
   10  ansible --version 
   11  ssh ec2-user@3.109.157.117
   12  ansible --version 
   13  vim /etc/ansible/ansible.cfg 
   14  head  /etc/ansible/ansible.cfg 
   15  head  -20 /etc/ansible/ansible.cfg 
   16  sudo vim /etc/ansible/hosts 
   17  sudo vi  /etc/ansible/hosts 
   18  unalias ls
   19  sudo vi  /etc/ansible/hosts 
   20  sudo nano  /etc/ansible/hosts 
   21  grep -in remote  /etc/ansible/ansible.cfg 
   22  sudo nano  /etc/ansible/ansible.cfg 
   23  grep -in remote  /etc/ansible/ansible.cfg 
   24  sudo vim  +107  /etc/ansible/ansible.cfg 
   25  107:remote_user = ec2-user
   26  history 
   27  ansible  web -m  ping  
   28  ansible  web1 -m  ping  
   29  ansible  web,database  -m  ping  
   30  ansible  all   -m  ping  
   31  ansible  all   -m  command -a  "date" 
   32  ansible  all   -m  command -a  "whoami" 
   33  ansible  all   -m  command -a  "pwd" 
   34  ansible  all   -m  command -a  "mkdir hello" 
   35  ansible  all   -m  command -a  "ls" 
   36  history 
   37  ansible  all   -m  command -a  "mkdir hello1 ; ls" 
   38  ansible  all   -m  command -a  "mkdir hello2 &&  ls" 
   39  ansible  all   -m  shell -a  "mkdir hello4 ;  ls" 
   40  history 
   41  ansible-doc -l 
   42  ansible-doc -l   |   grep  shell
   43  ansible-doc -l   |   grep  aws
   44  ansible-doc -l   |   grep  cisco
   45  ansible-doc -l   |   grep  ios
   46  history 
   47  ansible all -m command -a "mkdir  hello"
   54  cat httpd_install.yaml 
   55  vim httpd_install.yaml
   56  cat httpd_install.yaml 
   57  ansible-playbook   httpd_install.yaml 
   58  history 
   ```
   ## playbook of installation of httpd
   + create a yaml for eg:- httpd_ install.yaml
   ``` 
---
- hosts: all
  become: true
  tasks:
  - name: Install httpd software 
    yum:
     name: httpd
     state: present
```
