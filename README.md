[![linuxserver.io](https://raw.githubusercontent.com/linuxserver/docker-templates/master/linuxserver.io/img/linuxserver_medium.png)](https://linuxserver.io)

[![Blog](https://img.shields.io/static/v1.svg?style=flat-square&color=E68523&label=linuxserver.io&message=Blog)](https://blog.linuxserver.io "all the things you can do with our containers including How-To guides, opinions and much more!")
[![Discord](https://img.shields.io/discord/354974912613449730.svg?style=flat-square&color=E68523&label=Discord&logo=discord&logoColor=FFFFFF)](https://discord.gg/YWrKVTn "realtime support / chat with the community and the team.")
[![Discourse](https://img.shields.io/discourse/https/discourse.linuxserver.io/topics.svg?style=flat-square&color=E68523&logo=discourse&logoColor=FFFFFF)](https://discourse.linuxserver.io "post on our community forum.")
[![Fleet](https://img.shields.io/static/v1.svg?style=flat-square&color=E68523&label=linuxserver.io&message=Fleet)](https://fleet.linuxserver.io "an online web interface which displays all of our maintained images.")
[![GitHub](https://img.shields.io/static/v1.svg?style=flat-square&color=E68523&label=linuxserver.io&message=GitHub&logo=github&logoColor=FFFFFF)](https://github.com/linuxserver "view the source for all of our repositories.")
[![Open Collective](https://img.shields.io/opencollective/all/linuxserver.svg?style=flat-square&color=E68523&label=Supporters&logo=open%20collective&logoColor=FFFFFF)](https://opencollective.com/linuxserver "please consider helping us by either donating or contributing to our budget")

The [LinuxServer.io](https://linuxserver.io) team brings you another container release featuring :-

 * regular and timely application updates
 * easy user mappings (PGID, PUID)
 * custom base image with s6 overlay
 * weekly base OS updates with common layers across the entire LinuxServer.io ecosystem to minimise space usage, down time and bandwidth
 * regular security updates

Find us at:
* [Blog](https://blog.linuxserver.io) - all the things you can do with our containers including How-To guides, opinions and much more!
* [Discord](https://discord.gg/YWrKVTn) - realtime support / chat with the community and the team.
* [Discourse](https://discourse.linuxserver.io) - post on our community forum.
* [Fleet](https://fleet.linuxserver.io) - an online web interface which displays all of our maintained images.
* [GitHub](https://github.com/linuxserver) - view the source for all of our repositories.
* [Open Collective](https://opencollective.com/linuxserver) - please consider helping us by either donating or contributing to our budget

# [linuxserver/emby](https://github.com/linuxserver/docker-emby)

[![GitHub Stars](https://img.shields.io/github/stars/linuxserver/docker-emby.svg?style=flat-square&color=E68523&logo=github&logoColor=FFFFFF)](https://github.com/linuxserver/docker-emby)
[![GitHub Release](https://img.shields.io/github/release/linuxserver/docker-emby.svg?style=flat-square&color=E68523&logo=github&logoColor=FFFFFF)](https://github.com/linuxserver/docker-emby/releases)
[![GitHub Package Repository](https://img.shields.io/static/v1.svg?style=flat-square&color=E68523&label=linuxserver.io&message=GitHub%20Package&logo=github&logoColor=FFFFFF)](https://github.com/linuxserver/docker-emby/packages)
[![GitLab Container Registry](https://img.shields.io/static/v1.svg?style=flat-square&color=E68523&label=linuxserver.io&message=GitLab%20Registry&logo=gitlab&logoColor=FFFFFF)](https://gitlab.com/Linuxserver.io/docker-emby/container_registry)
[![Quay.io](https://img.shields.io/static/v1.svg?style=flat-square&color=E68523&label=linuxserver.io&message=Quay.io)](https://quay.io/repository/linuxserver.io/emby)
[![MicroBadger Layers](https://img.shields.io/microbadger/layers/linuxserver/emby.svg?style=flat-square&color=E68523)](https://microbadger.com/images/linuxserver/emby "Get your own version badge on microbadger.com")
[![Docker Pulls](https://img.shields.io/docker/pulls/linuxserver/emby.svg?style=flat-square&color=E68523&label=pulls&logo=docker&logoColor=FFFFFF)](https://hub.docker.com/r/linuxserver/emby)
[![Docker Stars](https://img.shields.io/docker/stars/linuxserver/emby.svg?style=flat-square&color=E68523&label=stars&logo=docker&logoColor=FFFFFF)](https://hub.docker.com/r/linuxserver/emby)
[![Build Status](https://ci.linuxserver.io/view/all/job/Docker-Pipeline-Builders/job/docker-emby/job/master/badge/icon?style=flat-square)](https://ci.linuxserver.io/job/Docker-Pipeline-Builders/job/docker-emby/job/master/)
[![](https://lsio-ci.ams3.digitaloceanspaces.com/linuxserver/emby/latest/badge.svg)](https://lsio-ci.ams3.digitaloceanspaces.com/linuxserver/emby/latest/index.html)

[Emby](https://emby.media/) organizes video, music, live TV, and photos from personal media libraries and streams them to smart TVs, streaming boxes and mobile devices. This container is packaged as a standalone emby Media Server.

[![emby](https://emby.media/community/uploads/inline/3/55626b855503c_logo800.png)](https://emby.media/)

## Supported Architectures

Our images support multiple architectures such as `x86-64`, `arm64` and `armhf`. We utilise the docker manifest for multi-platform awareness. More information is available from docker [here](https://github.com/docker/distribution/blob/master/docs/spec/manifest-v2-2.md#manifest-list) and our announcement [here](https://blog.linuxserver.io/2019/02/21/the-lsio-pipeline-project/).

Simply pulling `linuxserver/emby` should retrieve the correct image for your arch, but you can also pull specific arch images via tags.

The architectures supported by this image are:

| Architecture | Tag |
| :----: | --- |
| x86-64 | amd64-latest |
| arm64 | arm64v8-latest |
| armhf | arm32v7-latest |

## Version Tags

This image provides various versions that are available via tags. `latest` tag usually provides the latest stable version. Others are considered under development and caution must be exercised when using them.

| Tag | Description |
| :----: | --- |
| latest | Stable emby releases |
| beta | Beta emby releases |

## Usage

Here are some example snippets to help you get started creating a container.

### docker

```
docker create \
  --name=emby \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Europe/London \
  -e UMASK_SET=<022> `#optional` \
  -p 8096:8096 \
  -p 8920:8920 `#optional` \
  -v /path/to/library:/config \
  -v /path/to/tvseries:/data/tvshows \
  -v /path/to/movies:/data/movies \
  -v /path/for/transcoding:/transcode `#optional` \
  -v /opt/vc/lib:/opt/vc/lib `#optional` \
  --device /dev/dri:/dev/dri `#optional` \
  --device /dev/vchiq:/dev/vchiq `#optional` \
  --restart unless-stopped \
  linuxserver/emby
```


### docker-compose

Compatible with docker-compose v2 schemas.

```
---
version: "2"
services:
  emby:
    image: linuxserver/emby
    container_name: emby
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Europe/London
      - UMASK_SET=<022> #optional
    volumes:
      - /path/to/library:/config
      - /path/to/tvseries:/data/tvshows
      - /path/to/movies:/data/movies
      - /path/for/transcoding:/transcode #optional
      - /opt/vc/lib:/opt/vc/lib #optional
    ports:
      - 8096:8096
      - 8920:8920 #optional
    devices:
      - /dev/dri:/dev/dri #optional
      - /dev/vchiq:/dev/vchiq #optional
    restart: unless-stopped
```

## Parameters

Container images are configured using parameters passed at runtime (such as those above). These parameters are separated by a colon and indicate `<external>:<internal>` respectively. For example, `-p 8080:80` would expose port `80` from inside the container to be accessible from the host's IP on port `8080` outside the container.

| Parameter | Function |
| :----: | --- |
| `-p 8096` | Http webUI. |
| `-p 8920` | Https webUI (you need to setup your own certificate). |
| `-e PUID=1000` | for UserID - see below for explanation |
| `-e PGID=1000` | for GroupID - see below for explanation |
| `-e TZ=Europe/London` | Specify a timezone to use EG Europe/London |
| `-e UMASK_SET=<022>` | for umask setting of Emby, default if left unset is 022. |
| `-v /config` | Emby data storage location. *This can grow very large, 50gb+ is likely for a large collection.* |
| `-v /data/tvshows` | Media goes here. Add as many as needed e.g. `/data/movies`, `/data/tv`, etc. |
| `-v /data/movies` | Media goes here. Add as many as needed e.g. `/data/movies`, `/data/tv`, etc. |
| `-v /transcode` | Path for transcoding folder, *optional*. |
| `-v /opt/vc/lib` | Path for Raspberry Pi OpenMAX libs *optional*. |
| `--device /dev/dri` | Only needed if you want to use your Intel GPU for hardware accelerated video encoding (vaapi). |
| `--device /dev/vchiq` | Only needed if you want to use your Raspberry Pi OpenMax video encoding (Bellagio). |

## Environment variables from files (Docker secrets)

You can set any environment variable from a file by using a special prepend `FILE__`. 

As an example:

```
-e FILE__PASSWORD=/run/secrets/mysecretpassword
```

Will set the environment variable `PASSWORD` based on the contents of the `/run/secrets/mysecretpassword` file.

## User / Group Identifiers

When using volumes (`-v` flags) permissions issues can arise between the host OS and the container, we avoid this issue by allowing you to specify the user `PUID` and group `PGID`.

Ensure any volume directories on the host are owned by the same user you specify and any permissions issues will vanish like magic.

In this instance `PUID=1000` and `PGID=1000`, to find yours use `id user` as below:

```
  $ id username
    uid=1000(dockeruser) gid=1000(dockergroup) groups=1000(dockergroup)
```


&nbsp;
## Application Setup

Webui can be found at `http://<your-ip>:8096`

Emby has very complete and verbose documentation located [here](https://github.com/MediaBrowser/Wiki/wiki) .

Hardware acceleration users for Intel Quicksync will need to mount their /dev/dri video device inside of the container by passing the following command when running or creating the container:

```--device=/dev/dri:/dev/dri```

We will automatically ensure the abc user inside of the container has the proper permissions to access this device.

Hardware acceleration users for Nvidia will need to install the container runtime provided by Nvidia on their host, instructions can be found here:

https://github.com/NVIDIA/nvidia-docker

We automatically add the necessary environment variable that will utilise all the features available on a GPU on the host. Once nvidia-docker is installed on your host you will need to re/create the docker container with the nvidia container runtime `--runtime=nvidia` and add an environment variable `-e NVIDIA_VISIBLE_DEVICES=all` (can also be set to a specific gpu's UUID, this can be discovered by running `nvidia-smi --query-gpu=gpu_name,gpu_uuid --format=csv` ). NVIDIA automatically mounts the GPU and drivers from your host into the emby docker.

### OpenMAX (Raspberry Pi)

Hardware acceleration users for Raspberry Pi OpenMAX will need to mount their /dev/vchiq video device inside of the container and their system OpenMax libs by passing the following options when running or creating the container:
```
--device=/dev/vchiq:/dev/vchiq
-v /opt/vc/lib:/opt/vc/lib
```



## Support Info

* Shell access whilst the container is running: `docker exec -it emby /bin/bash`
* To monitor the logs of the container in realtime: `docker logs -f emby`
* container version number
  * `docker inspect -f '{{ index .Config.Labels "build_version" }}' emby`
* image version number
  * `docker inspect -f '{{ index .Config.Labels "build_version" }}' linuxserver/emby`

## Updating Info

Most of our images are static, versioned, and require an image update and container recreation to update the app inside. With some exceptions (ie. nextcloud, plex), we do not recommend or support updating apps inside the container. Please consult the [Application Setup](#application-setup) section above to see if it is recommended for the image.

Below are the instructions for updating containers:

### Via Docker Run/Create
* Update the image: `docker pull linuxserver/emby`
* Stop the running container: `docker stop emby`
* Delete the container: `docker rm emby`
* Recreate a new container with the same docker create parameters as instructed above (if mapped correctly to a host folder, your `/config` folder and settings will be preserved)
* Start the new container: `docker start emby`
* You can also remove the old dangling images: `docker image prune`

### Via Docker Compose
* Update all images: `docker-compose pull`
  * or update a single image: `docker-compose pull emby`
* Let compose update all containers as necessary: `docker-compose up -d`
  * or update a single container: `docker-compose up -d emby`
* You can also remove the old dangling images: `docker image prune`

### Via Watchtower auto-updater (especially useful if you don't remember the original parameters)
* Pull the latest image at its tag and replace it with the same env variables in one run:
  ```
  docker run --rm \
  -v /var/run/docker.sock:/var/run/docker.sock \
  containrrr/watchtower \
  --run-once emby
  ```

**Note:** We do not endorse the use of Watchtower as a solution to automated updates of existing Docker containers. In fact we generally discourage automated updates. However, this is a useful tool for one-time manual updates of containers where you have forgotten the original parameters. In the long term, we highly recommend using Docker Compose.

* You can also remove the old dangling images: `docker image prune`

## Building locally

If you want to make local modifications to these images for development purposes or just to customize the logic:
```
git clone https://github.com/linuxserver/docker-emby.git
cd docker-emby
docker build \
  --no-cache \
  --pull \
  -t linuxserver/emby:latest .
```

The ARM variants can be built on x86_64 hardware using `multiarch/qemu-user-static`
```
docker run --rm --privileged multiarch/qemu-user-static:register --reset
```

Once registered you can define the dockerfile to use with `-f Dockerfile.aarch64`.

## Versions

* **26.02.20:** - Add openmax support on Raspberry Pi.
* **15.02.20:** - Allow restarting emby from the gui (also allows for auto restarts after addon updates).
* **02.10.19:** - Improve permission fixing for render and dvb devices.
* **13.08.19:** - Add umask environment variable.
* **30.05.19:** - Initial release.
