ADD -- Copia novos arquivos, diretórios, arquivos TAR ou arquivos remotos e os adiciona ao filesystem do container.

CMD -- Executa um comando. Diferentemente do RUN, que executa o comando no momento em que está "buildando" a imagem, o CMD irá fazê-lo somente quando o container é iniciado.

LABEL -- Adiciona metadados à imagem, como versão, descrição e fabricante.

COPY -- Copia novos arquivos e diretórios e os adiciona ao filesystem do container.

ENTRYPOINT -- Permite que você configure um container para rodar um executável. Quando esse executável for finalizado, o container também será.

ENV -- Informa variáveis de ambiente ao container.

EXPOSE -- Informa qual porta o container estará ouvindo.

FROM -- Indica qual imagem será utilizada como base. Ela precisa ser a primeira linha do dockerfile.

MAINTAINER -- Autor da imagem.

RUN -- Executa qualquer comando em uma nova camada no topo da imagem e "commita" as alterações. Essas alterações você poderá utilizar nas próximas instruções de seu dockerfile.

USER -- Determina qual usuário será utilizado na imagem. Por default é o root.

VOLUME -- Permite a criação de um ponto de montagem no container.

WORKDIR -- Responsável por mudar do diretório "/" (raiz) para o especificado nele.
```bash
FROM ubuntu:16.04
RUN apt-get update
RUN apt-get install nginx
RUN apt-get install php5
COPY arquivo_teste /tmp/arquivo_teste
CMD bash
```
