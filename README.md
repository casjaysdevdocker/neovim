## 👋 Welcome to neovim 🚀  

neovim README  
  
  
## Run container

```shell
dockermgr update neovim
```

### via command line

```shell
docker pull casjaysdevdocker/neovim:latest && \
docker run -d \
--restart always \
--name casjaysdevdocker-neovim \
--hostname casjaysdev-neovim \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/docker/storage/neovim/neovim/data:/data \
-v $HOME/.local/share/docker/storage/neovim/neovim/config:/config \
-p 80:80 \
casjaysdevdocker/neovim:latest
```

### via docker-compose

```yaml
version: "2"
services:
  neovim:
    image: casjaysdevdocker/neovim
    container_name: neovim
    environment:
      - TZ=America/New_York
      - HOSTNAME=casjaysdev-neovim
    volumes:
      - $HOME/.local/share/docker/storage/neovim/data:/data:z
      - $HOME/.local/share/docker/storage/neovim/config:/config:z
    ports:
      - 80:80
    restart: always
```

## Authors  

🤖 casjay: [Github](https://github.com/casjay) [Docker](https://hub.docker.com/r/casjay) 🤖  
⛵ CasjaysDevdDocker: [Github](https://github.com/casjaysdev) [Docker](https://hub.docker.com/r/casjaysdevdocker) ⛵  
