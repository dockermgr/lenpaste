## 👋 Welcome to lenpaste 🚀  

lenpaste README  
  
  
## Requires scripts to be installed  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 systemmgr --config && systemmgr install scripts  
```

## Automatic install/update  

```shell
dockermgr update lenpaste
```

OR

```shell
mkdir -p "$HOME/.local/share/srv/docker/lenpaste/dataDir"
git clone "https://github.com/dockermgr/lenpaste" "$HOME/.local/share/CasjaysDev/dockermgr/lenpaste"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/lenpaste/dataDir/." "$HOME/.local/share/srv/docker/lenpaste/dataDir/"
```

## via command line  

```shell
docker pull casjaysdevdocker/lenpaste:latest && \
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-lenpaste \
--hostname casjaysdev-lenpaste \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/lenpaste/dataDir/data:/data:z \
-v $HOME/.local/share/srv/docker/lenpaste/dataDir/config:/config:z \
-p 80:80 \
casjaysdevdocker/lenpaste:latest
```

## via docker-compose  

```yaml
version: "2"
services:
  lenpaste:
    image: casjaysdevdocker/lenpaste
    container_name: lenpaste
    environment:
      - TZ=America/New_York
      - HOSTNAME=casjaysdev-lenpaste
    volumes:
      - $HOME/.local/share/srv/docker/lenpaste/dataDir/data:/data:z
      - $HOME/.local/share/srv/docker/lenpaste/dataDir/config:/config:z
    ports:
      - 80:80
    restart: always
```

## Author  

📽 dockermgr: [Github](https://github.com/dockermgr) 📽  
🤖 casjay: [Github](https://github.com/casjay) [Docker](https://hub.docker.com/r/casjay) 🤖  
⛵ CasjaysDevDocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/r/casjaysdevdocker) ⛵  
