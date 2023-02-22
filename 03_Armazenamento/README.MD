# volumes 

## Comandos básicos

```bash
  # Apreenta todos os volumes 
  Docker volume ls
```

<h1>Os volumes guardam os dados. Os volumes de dados quando criados no container são apontados para uma pequena pasta no docker host a onde ficam retidos sem perde-los.</h1> 

- Isso faz com que não percamos os nossos dados, pois o *container* até pode ser removido, mas a pasta no **Docker Host** ficará intacta.
## sintaxe da flag -v ou --volume:
EX: 
```bash
-v mysql-db:/var/lib/mysql:ro
```
- mysql-db - Volume nomeado no Docker Host
- /var/lib/mysql - diretório dentro do container
- ro - este campo é opcional, é possível informar se o volume é read only (ro) ou read write (rw). O padrão é RW.

## sintaxe da flag --mount (Composta por chave e valor):<br>
```bash
--mount'type=volume,source=mysql-db,target=/var/lib/mysql,readonly'
```
- mysql-db - Volume nomeado no Docker Host. Podemos chamar através do source ou src
- /var/lib.mysql - diretório dentro do container. Podemos chamar através de destination, dst ou target
- readonly - este campo é opcional, é possível informar se o volume é read-only ou read-write. O padrão é read-write.

# Bind Mounts 
```bash
# "--mount" = Especifica que o Mount será realizado

# "type" = Especifica o tipo do mount que será realizado

# "source" = Caminho na máquina da pasta que será refletida no container

# "target" = Caminho no container onde será refletido o mount

# PS: "$(pwd)" funciona como uma abreviação para o caminho absoluto que seria informado, ele pega o caminho relativo de onde o comando está sendo executado.
```
## sintaxe da flag -v ou --volume
```bash
-v $(pwd)/mysql:var/lib/mysql
```
- -v $(pwd)/mysql - Caminho do diretório local
- var/lib/mysql - Diretório dentro do container
- ro - Este campo é opcional, é possível informar se o volume é read only (ro) ou read write (rw). O padrão é RW.
## sintaxe da flag --mount(Comporta por chave e valor):
```bash
--mount'type=volume,source=$(pwd)/mysql,target=/var/lib/mysql,readonly'
```
- $(pwd)/mysql - Caminho do diretório local. Podemos chamar através do source ou src
- /var/lib/mysql - diretório dentro do container. Podemos chamar através de destination, dst ou target.
- readonly - este campo é opcional, é possível informar se o volume é read-only ou read-write. O padrão é read-write.

docker run -d --name nginx -p 8080:80 --mount type=bind,source="$(pwd)"/html,target=/usr/share/nginx/html 
