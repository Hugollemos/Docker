# O Docker Swarm é uma ferramenta do Docker que permite criar e gerenciar um cluster de hosts Docker, formando um ambiente de orquestração de containers. Ele fornece recursos para lidar com a execução e escalabilidade de aplicativos distribuídos em vários nós do Docker.

## Para praticar https://labs.play-with-docker.com

## Para iniciar o swarm dentro da máquina
```
docker swarm init --advertise-addr [ip do host]
```
saida:
``````
Swarm initialized: current node (2qacv429fvnret8v09fqmjm16) is now a manager.

To add a worker to this swarm, run the following command:

   docker swarm join --token SWMTKN-1-100qtga34hfnf14xdbbhtv8ut6ugcvuhsx427jtzwaw1td2otj-18wccykydxte59gch2pix 172.31.58.90:2377

To add a manager to this swarm, run 'docker swarm join-token manager' and follow the instructions.
``````
Essa saída é usada para adicionar outras máquinas ao cluster
```
docker swarm join --token SWMTKN-1-100qtga34hfnf14xdbbhtv8ut6ugcvuhsx427jtzwaw1td2otj-18wccykydxte59gch2pix 172.31.58.90:2377
```

## Comando para pegar o token do manager
```
docker swarm join-token manager
```
## Comando para pegar o token do worker
```
docker swarm join-token worker
```
## Para promover um nó para manager
```
docker node promote <nome do nó>
```
### Para tornar um node manager em worker
```
docker node demote [nome do nó]
```
### Removendo o node do cluster
``````
docker swarm leave
``````
### removendo o node
``````
docker node rm
``````
### removendo um node manager do cluster
``````
docker swarm leave --force
``````

# SERVICES
...