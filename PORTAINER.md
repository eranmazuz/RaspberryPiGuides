# Installing portainer on a Raspberry PI

## Requirements
* docker installed.


## Commands
    sudo docker pull portainer/portainer-ce:latest
    sudo mkdir -p /portainer/Files/AppData/Config/portainer
    sudo docker run -d -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v /portainer/Files/AppData/Config/portainer:/data portainer/portainer-ce:latest
