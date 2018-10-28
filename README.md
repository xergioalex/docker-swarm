Docker Swarm Simple Example
---

Here example follow the oficial docker guide: https://docs.docker.com/get-started/part5/#add-a-new-service-and-redeploy


Create a swarm
```
# Create machines
docker-machine create machine1
docker-machine create machine2
docker-machine create machine3
docker-machine create machine4
docker-machine create machine5

# Init swarm
docker swarm init
docker swarm init --advertise-addr idaddr
# Join as worker
docker swarm join-token -q worker
docker swarm join --token SWMTKN-1-35tpwd5imtgtmudylaq5ixt9uvo9x8iue6of6qhjam1axadbsg-czaxs1uzyalmxz12hquop78ye idaddr:2377
# Join as manager
docker swarm join-token manager
```


Deploy services
```
docker stack deploy -c docker-compose.yml myservicename
docker stack ps myservicename
docker stack rm myservicename
```