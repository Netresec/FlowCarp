# FlowCarp
[FlowCarp](https://flowcarp.com/) identifies application-layer protocols in network traffic based on behavior instead of port numbers. FlowCarp reads packet data in the form of PCAP, PcapNG or TZSP streams and outputs information about the flows it finds, including the detected application layer protocol for each flow.

<img src="https://flowcarp.com/images/FlowCarp_2000x2000.webp" alt="FlowCarp logo" width="400" alt="FlowCarp logo" style="max-width: 20%; height: auto;" />

More information about FlowCarp can be found on the [official FlowCarp website](https://flowcarp.com/).

# Install as Container
Install docker container from command line:

`docker pull ghcr.io/netresec/flowcarp:latest`

Or better yet, use our [docker-compose.yml](docker-compose.yml) to install the docker container:
```
curl -fsSL https://raw.githubusercontent.com/Netresec/FlowCarp/refs/heads/main/docker-compose.yml -o docker-compose.yml
docker compose up -d
```

# Environment Variables

The following environment variables can be set to configure FlowCarp.

```
FC_CLEARCACHE           Clear cached data and protocols
FC_DEBUG                Log debug info
FC_FLUSH=<seconds>      Flush active flows every <seconds>. For real-time monitoring. Can output flow duplicates.
FC_FORMAT=<format>      Flow output format, where <format> can be:
   CSV                  Comma separated values (default)
   TSV                  Tab separated values
   EveJson              Suricata Eve JSON, alerts and flows
   EveJsonAlert         Suricata Eve JSON, alerts only
   EveJsonFlow          Suricata Eve JSON, flows only
   ZeekConn             Zeek conn log, flows only
   ZeekNotice           Zeek notice log, alerts only
FC_HELP                 Print command line argument help and quit
FC_HELPENV              Print supported environment variables and quit
FC_INPUT=<source>       Network traffic/packet input, where <source> can be:
   FILE                 Read pcap(ng) file from path specified in FILE
   URI                  Download pcap(ng) file from URI
   -                    Read pcap(ng) stream from stdin
   directory:<mode>:PATH   Search for pcap(ng) files in PATH, where <mode> can be:
      Once              Process files in PATH, then quit
      OnceRecursive     Process files in PATH and sub directories thereof, then quit
      Monitor           Process files in PATH, then monitor for new files to process in PATH
   tcp[:IP]:PORT        Start PCAP-over-IP listener on TCP port, for example tcp:57012. Default IP is 0.0.0.0
   tcpconnect:IP:PORT   Connect to a PCAP-over-IP server, such as PolarProxy or Fox-IT's pcap-broker.
   tzsp[:IP]:PORT       Listen for MikroTik TZSP stream(s) on UDP port, for example tzsp:37008. Default IP is 0.0.0.0
FC_KEY=<license>        Use license key <license> to identify more protocols
FC_KEYFILE=<path>       Read license key from <path> to identify more protocols
FC_LOGTIME              Include timestamps in log output
FC_MODEL=<file>         Load custom protocol model from file (create with --output model)
FC_OUTPUT=<type>        Output flow data as <type>, which can be any of:
   FILE                 Write flow data to FILE
   DIR                  Write flow data to new file in DIR
   -                    Output flow data to stdout
   tcp[:IP]:PORT        Create flow output service listening on specified TCP port. Default IP is 0.0.0.0
   tcpconnect:IP:PORT   Send flow output to specified IP and TCP port
   model:PROTO:[TAGS]:FILE   Generate custom protocol model for PROTO from input packets and save it to .fcp FILE. Use comma separated TAGS, such as MALICIOUS,COINMINER (MALICIOUS is required to generate alerts).
   ipfix:PORT           NOT IMPLEMENTED
FC_PREVIEW              Output early preview of active flows. For real-time monitoring. Can output flow duplicates.
FC_REALTIME             Read input pcap data at maximum speed, with risk of dropping some frames
FC_TIMEOUT=<seconds>    Input timeout. Default = 0 (no timeout).
FC_VERBOSE              Log more information to stderr
FC_VERSION              Show version number and quit
FC_WEBSERVICE=<uri-prefix>   Start pcap-to-flows web service on URI prefix, such as http://127.0.0.1:57080/ or http://+:57080/
```
