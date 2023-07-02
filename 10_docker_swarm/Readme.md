# O Docker Swarm é uma ferramenta do Docker que permite criar e gerenciar um cluster de hosts Docker, formando um ambiente de orquestração de containers. Ele fornece recursos para lidar com a execução e escalabilidade de aplicativos distribuídos em vários nós do Docker.

## Para praticar https://labs.play-with-docker.com

## Para iniciar o swarm dentro da máquina
```
docker swarm init --advertise-addr [ip do host]
```

## Comando para criar a máquina
```
docker-machine create -d virtualbox [nome]
```

## Comando para pegar o token do manager
```
docker swarm join-token manager
```
## Para promover um nó para manager
```
docker node promote <nome do nó>
```

