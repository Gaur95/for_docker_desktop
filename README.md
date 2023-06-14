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
