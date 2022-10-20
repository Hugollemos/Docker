# volumes 
os volumes sao os lugares a onde sao guardados os dados
os volumes de dados sao apontados para uma pequena pasta no docker host, quando criamos um volume, tbm criamos uma pasta no container e tudo que é escrito dentro dessa pasta tbm é escrito no docker host 

- Isso faz com que não percamos os nossos dados, pois o *container*
 até pode ser removido, mas a pasta no **Docker Host**
 ficará intacta.

tudo que for criado no na pasta por exemplo: /var/www tbm sera criado na pasta loca que o docker cria, exemplo: **var/lib/docker/volumes/5e1cbfd48d07284680552e56087c9d5196659600ccd6874bfa3831b51ddd0576**

percorrendo o caminho contrario, podemos escrever na pasta que criamos localmente para que seja espelhada na pasta do container, assim não precisaremos ter certas ferramentas instaladas nas máquina, fazendo com que, o container rode o que for passado na pasta local, sem ser de fato instaladas.

P.S: rever as aulas da etapa 3 fazer um teste em casa com outra linguagem para ver se funciona mesmo