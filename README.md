# install portainer on windows 10
# https://portainer.readthedocs.io/en/stable/deployment.html#deploying-portainer-on-windows


# install docker
# https://docs.docker.com/docker-for-windows/install/

# pull portainer image
```powershell
docker pull portainer/portainer-ee
```



# install portainer
```powershell
docker volume create portainer_data
docker run -d -p 9000:9000 --name=portainer --restart=always -v \\.\pipe\docker_engine:\\.\pipe\docker_engine -v portainer_data:C:\data portainer/portainer-ee
```
# portainer license
# https://portainer.readthedocs.io/en/stable/faq.html#how-do-i-get-a-portainer-license

# open portainer
http://localhost:9000

# login
username: admin
password: admin

# create a new user
# https://portainer.readthedocs.io/en/stable/users.html#creating-a-new-user

# uninstall portainer
```powershell
docker stop portainer
docker rm portainer
docker volume rm portainer_data
```

# update portainer
```powershell
docker pull portainer/portainer
docker stop portainer
docker rm portainer
docker volume create portainer_data
docker run -d -p 9000:9000 --name=portainer --restart=always -v \\.\pipe\docker_engine:\\.\pipe\docker_engine -v portainer_data:C:\data portainer/portainer
```

