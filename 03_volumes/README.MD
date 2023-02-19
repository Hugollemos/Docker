# volumes 

## Comandos básicos

```bash
  # Apreenta todos os volumes 
  Docker volume ls
```

<h1>Os volumes são os lugares a onde são guardados os dados.
Os volumes de dados quando criados no container são apontados para uma pequena pasta no docker host a onde ficam retidos sem perde-los.</h1> 

- Isso faz com que não percamos os nossos dados, pois o *container* até pode ser removido, mas a pasta no **Docker Host** ficará intacta.

- tudo que for criado no na pasta por exemplo: /var/www também sera criado na pasta local que o docker cria, exemplo: **var/lib/docker/volumes/5e1cbfd48d07284680552e56087c9d5196659600ccd6874bfa3831b51ddd0576**(que podemos alterar).

P.S: percorrendo o caminho contrario, podemos escrever na pasta que criamos localmente para que seja espelhada na pasta do container, assim não precisaremos ter certas ferramentas instaladas nas máquina, fazendo com que, o container rode o que for passado na pasta local, sem ser de fato instaladas.


# Volumes


# Bind Mounts
```bash
# "--mount" = Especifica que o Mount será realizado

# "type" = Especifica o tipo do mount que será realizado

# "source" = Caminho na máquina da pasta que será refletida no container

# "target" = Caminho no container onde será refletido o mount

# PS: "$(pwd)" funciona como uma abreviação para o caminho absoluto que seria informado, ele pega o caminho relativo de onde o comando está sendo executado.

docker run -d --name nginx -p 8080:80 --mount type=TIPO_DO_MOUNT,source=CAMINHO_DA_PASTA_A_SER_MONTADA,target=CAMINHO_DENTRO_DO_CONTAINER_ONDE_A_PASTA_VAI_SER_MONTADA

# EX:

docker run -d --name nginx -p 8080:80 --mount type=bind,source="$(pwd)"/html,target=/usr/share/nginx/html
```

P.S Olhar na documentação 