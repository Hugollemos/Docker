# Configurando CPU e memória para os meus containers

## Especificando a quantidade de memória

```bash
# Criando o container
docker container run -ti --name teste debian
```

```bash
# Visualizando a quantidade de memória
docker container inspect teste | grep -i mem
```

```bash
# Subindo um novo container, porém passando os valores para que utilize 512 MB de memória:

Docker container run -ti -m 512M --name novo_container debian
```

docker container run --cpus=0.5 --name teste1 nginx

# Alterando a CPU e memória dos containers em execução

docker container run -ti --cpus=4 -m 512m --name teste1 nginx

docker container update -m 256m --cpus=1 teste1


# estressando o sistema

## Instalando o stress
```
apt-get update && apt-get install stress
```

## Estressndo a cpu
```
stress --cpu <número de threads>
```

## Estressando a Memory
```
stress --vm <número de workers> --vm-bytes <tamanho da memória em bytes>
```

## I/O stress
```
stress --io <número de workers>
```
## Container de estress
link: https://hub.docker.com/r/progrium/stress

