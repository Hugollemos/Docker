
ADD -- O papel do ADD é fazer a cópia de um arquivo, diretório ou até mesmo fazer o download de uma URL de nossa máquina host e colocar dentro da imagem.

COPY -- A instrução COPY, permite apenas a passagem de arquivos ou diretórios, diferente do ADD, que permite downloads. 

OBS: As instruções ADD e COPY tem propósitos semelhantes, copiar do host para a imagem. Porém existem diferenças no uso.

CMD -- Executa um comando. Diferentemente do RUN, que executa o comando no momento em que está "buildando" a imagem, o CMD irá fazê-lo somente quando o container é iniciado.

LABEL -- Adiciona metadados à imagem, como versão, descrição e fabricante.

ENTRYPOINT -- Permite que você configure um container para rodar um executável. 

ENV -- Informa variáveis de ambiente ao container.

EXPOSE -- Somente informa qual porta o container estará ouvindo.

FROM -- Indica qual imagem será utilizada como base. Ela precisa ser a primeira linha do dockerfile.

MAINTAINER -- Autor da imagem.

RUN -- Executa qualquer comando em uma nova camada no topo da imagem e "commita" as alterações. Essas alterações você poderá utilizar nas próximas instruções de seu dockerfile.

USER -- Determina qual usuário será utilizado na imagem. Por default é o root.

VOLUME -- Essa instrução cria uma pasta em nosso container que será compartilhada entre o container e o host. Todo arquivo criado dentro dessa pasta será acessível a partir da máquina host no caminho /var/lib/docker/volumes.

WORKDIR -- Responsável por mudar do diretório "/" (raiz) para o especificado nele.<br>

Ex de Dockerfile
```bash
FROM ubuntu:16.04
RUN apt-get update
RUN apt-get install nginx
RUN apt-get install php5
COPY arquivo_teste /tmp/arquivo_teste
CMD bash
```