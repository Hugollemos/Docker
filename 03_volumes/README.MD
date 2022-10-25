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