# FlowCarp
Assets and resources for [FlowCarp](https://flowcarp.com/).

<img src="https://flowcarp.com/images/FlowCarp_2000x2000.webp" alt="FlowCarp logo" style="float: right; width: 30%; height: auto; margin: 3%;" />

Install docker container from command line:

`docker pull ghcr.io/netresec/flowcarp:latest`

Or better yet, use our [docker-compose.yml](docker-compose.yml) to install the docker container:
```
curl -sSL https://github.com/Netresec/FlowCarp/raw/refs/heads/main/docker-compose.yml -o docker-compose.yml

docker compose build
docker compose up
```
