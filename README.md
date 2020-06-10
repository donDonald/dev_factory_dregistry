# Docker registry + docker-registry-ui



### Use-cases
- I'm a developer and need quckly to setup a docker registry. I don't mind SSL or authentication.



### Details
It's a docker-compose file containing 2 services:
```
$ docker-compose ps
       Name               Command          State                                          Ports                                    
-----------------------------------------------------------------------------------------------------------------------------------
dregistry_dregistry-ui_1   /bin/sh -c entrypoint            Up      0.0.0.0:11132->80/tcp  
dregistry_dregistry_1      /entrypoint.sh /etc/docker ...   Up      0.0.0.0:11131->5000/tcp
```



### Cridentials
Here are no predefined cridentials as such



### To launch
```
$ docker-compose up -d --build
```



### Append dregistry to /etc/hosts
```
$ echo "$(docker exec -it dregistry_dregistry_1 sh -c "hostname -i" | head -c-2) $(docker exec -it dregistry_dregistry_1 sh -c "hostname" | head -c-2)" >> /etc/hosts
```



### To shutdown
```
$ docker-compose down
```



### To cleanup volumes
```
$ docker volume rm dregistry_dregistry-data
```



### Web services
- [localhost](http://localhost:11132)

