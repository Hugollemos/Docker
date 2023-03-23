# NETWORK

## Comandos básicos

```bash
# Comando para ver o IP atribuído pela rede local do docker.
hostname -i
```

```bash
# Cria uma Network com as insformações especificadas

docker network create --drive NETWORK_TYPE NETWORK_NAME

# EX:

docker network create --driver bridge minharede
```
O comando _docker network create_ cria uma rede no Docker.
O comando _--driver_ é usdo para criar uma rede. Obs:existem vários drivers de rede.

```bash
# Exibe informações da network especificada

docker network inspect NETWORK_NAME

# EX:

docker network inspect bridge
```

## Conectando container já em execução a uma network

```bash
# Conecta o container a rede especificada

docker network connect NETWORK_NAME CONTAINER_NAME

# EX:

docker network connect minharede ubuntu3
```