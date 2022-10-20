# Kickstart

## Comandos básicos 

```bash
# Exibe todos os containers em execução na máquina
docker ps

# Exibe todos os container ativos ou inativos existentes na máquina
docker ps -a
```

```bash
# Executa o container com o nome informado
docker run IMAGE_NAME

# Especificando a imagem e a versão
docker run IMAGE_NAME:IMAGE_VERSION
```

```bash
# Permite remover todos os containers inativos de uma só vez.
docker container prune

# Permite remover imagens
docker rmi [CONTAINER ID]
```

```bash
# Permite remover containers
docker rm [CONTAINER ID]

# Permite riar um container sem execução 
docker container create -ti ubuntu
```

## Interação com o container
```bash
# "-t" -- Disponibiliza um TTY (console) para o nosso container.

# "-i" -- Mantém o STDIN aberto mesmo que você não esteja conectado no container.

# "-d" = detach, Efetua a desassociação do processo do terminal com o processo do container

# Com isso temos dois modos de execução de nossos containers: modo interativo ou daemonizando o container.
docker run -i -t ubuntu

# ou

docker run -it ubuntu

# ou

docker run -d ubuntu
```

```bash
# Saindo do container em execução
CTRL + P + Q

# Entrando no container em execução
docker container attach <CONTAINER ID>

# ou
docker exec -it [nome container] bash
```

```bash
# Executar um container
docker container start [CONTAINER ID] 

# ou

# flag attach: "-a" | flag interactive: "-i"
docker start -a -i [CONTAINER ID] 

# Para matar o container == sair do container
CTRL + C
```

```bash
# Parando um container
docker container stop [CONTAINER ID]

# Reiniciando um container
docker container restart [CONTAINER ID]
```

```bash
# Pausando um container
docker container pause [CONTAINER ID]

# Despausando um container
docker container unpause [CONTAINER ID]
```

```bash
# Visualizando o consumo do container
docker container stats [CONTAINER ID]

# Removendo um container
docker rm CONTAINER_ID

# ou
docker rm CONTAINER_NAME

# PS: O container morre quando o processo rodando acaba.
```

## Parando todos os containers que estão rodando, de uma só vez
```bash
docker stop $(docker ps -q)
```

## Conectando a um site de dentro do container 
```bash
# Flag: "-p" fará com que o Docker atribua uma porta aleatória do mundo externo,(minha máquina), para poder se comunicar com o que está dentro do container:
docker run -d -P dockersamples/static-site
```

```bash
# Vendo as portas do container
docker port [CONTAINER ID]
```

## Definindo uma porta específica
```bash
docker run -d -p 12345:80 dockersamples/static-site
```

## Nomeando containers
```bash
EX:
docker run -d -P --name meu-site dockersamples/static-site
```