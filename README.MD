# PORT TRACKER CONTAINERLAB

## Import the cEOS Image

```
docker import cEOS64-lab-4.32.0F.tar.xz ceos:4.32.0F
```

## Install Containerlab

```
curl -sL https://containerlab.dev/setup | sudo bash -s "all"
```

## Deploy the lab

```
containerlab deploy -t topology.yml
```

### Verify Lab

```
containerlab inspect -t topology.yml
```

From here you can see the layout and IP addresses of the lab

```
udo containerlab inspect -t topology.yml 
INFO[0000] Parsing & checking topology file: topology.yml 
+---+----------------------------+--------------+--------------+-------+---------+----------------+--------------+
| # |            Name            | Container ID |    Image     | Kind  |  State  |  IPv4 Address  | IPv6 Address |
+---+----------------------------+--------------+--------------+-------+---------+----------------+--------------+
| 1 | clab-port-tracker-lab-ceos | b85c768491ae | ceos:4.32.1F | ceos  | running | 192.168.2.4/24 | N/A          |
| 2 | clab-port-tracker-lab-pc1  | 8c5e06260d9a | alpine       | linux | running | 192.168.2.2/24 | N/A          |
| 3 | clab-port-tracker-lab-pc2  | 7efd85844dd5 | alpine       | linux | running | 192.168.2.5/24 | N/A          |
| 4 | clab-port-tracker-lab-pc3  | 2dee56ae3c9f | alpine       | linux | running | 192.168.2.3/24 | N/A          |
```

### Connecting to cEOS node

You can use SSH to connect

```
ssh admin@<ip-of-node>
```
