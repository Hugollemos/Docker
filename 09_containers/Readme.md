# O que são containers ?
>Um container é um padrão de unidade de software que empacota código e todas as dependencias de uma aplicação que a mesma seja executada rapidamente de forma confiável de um ambiente computacional para o outro.

# Namespaces 
Reponsável por gerar isolamente de grupos de processos em seu nível lógico, como o gerenciamento de suários, rede, etc. garantido que o container não enxergue os processos do host e vice-versa. 

# Cgroups
Para gerenciar os recursos físicos que são compartilhados entre esses processos existe o Cgroups. Ele fornece ao Docker o poder de compartilhar CPU, memória, I/O, etc., entre o host e o container. Além disso, é possível limitar ou restringir esses recursos para containers específicos.

# Overlay File System
