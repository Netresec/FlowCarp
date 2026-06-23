# FlowCarp
FlowCarp identifies application-layer protocols in network traffic based on behavior instead of port numbers. FlowCarp reads packet data in the form of PCAP, PcapNG or TZSP streams and outputs information about the flows it finds, including the detected application layer protocol for each flow.

<img src="https://flowcarp.com/images/FlowCarp_2000x2000.webp" alt="FlowCarp logo" width="400" alt="FlowCarp logo" style="max-width: 20%; height: auto;" />

More information about FlowCarp can be found on the [official FlowCarp website](https://flowcarp.com/).

# Install as Container
Install docker container from command line:

`docker pull ghcr.io/netresec/flowcarp:latest`

Or better yet, use our [docker-compose.yml](docker-compose.yml) to install the docker container:
```
curl -fsSL https://github.com/Netresec/FlowCarp/raw/refs/heads/main/docker-compose.yml -o docker-compose.yml
docker compose up -d
```

# Download Binaries

Pre-compiled binaries for Linux, macOS and Windows can be downloaded from the [official FlowCarp website](https://flowcarp.com/).
