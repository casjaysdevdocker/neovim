## 👋 Welcome to neovim 🚀  

neovim README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update neovim
```
  
## Install and run container
  
```shell
dockerHome="/var/lib/srv/$USER/docker/casjaysdevdocker/neovim/neovim/latest/rootfs"
mkdir -p "/var/lib/srv/$USER/docker/neovim/rootfs"
git clone "https://github.com/dockermgr/neovim" "$HOME/.local/share/CasjaysDev/dockermgr/neovim"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/neovim/rootfs/." "$dockerHome/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-neovim-latest \
--hostname neovim \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$dockerHome/data:/data:z" \
-v "$dockerHome/config:/config:z" \
-p 80:80 \
casjaysdevdocker/neovim:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/neovim
    container_name: casjaysdevdocker-neovim
    environment:
      - TZ=America/New_York
      - HOSTNAME=neovim
    volumes:
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/neovim/neovim/latest/rootfs/data:/data:z"
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/neovim/neovim/latest/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/neovim
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/neovim" "$HOME/Projects/github/casjaysdevdocker/neovim"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/neovim"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
