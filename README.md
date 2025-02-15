#### Network commands

```
docker container prune -f
```

```
docker network create --subnet=10.0.0.0/24 net1
docker network create --subnet=10.0.1.0/24 net2
```

```
docker run -itd --name cont1 --network net1 --cap-add=NET_ADMIN ghcr.io/pranavg1203/meta:alpine sh
```

```
docker run -itd --name cont2 --network net2 --cap-add=NET_ADMIN ghcr.io/pranavg1203/meta:alpine sh
```

```
docker run -itd --name gw ghcr.io/pranavg1203/meta:alpine sh
```

```
ip route add 10.0.0.0/24 via 10.0.1.3
```

```
ip route add 10.0.1.0/24 via 10.0.0.3
```
