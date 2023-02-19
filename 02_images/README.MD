# Images
<h1>Traçando um paralelo com o conceito de orientação a objeto, a imagem é a classe e o container o objeto. A imagem é a abstração da infraestrutura em estado somente leitura, de onde será instanciado o container.

Todo container é iniciado a partir de uma imagem, dessa forma podemos concluir que nunca teremos uma imagem em execução.

Um container só pode ser iniciado a partir de uma única imagem. Caso deseje um comportamento diferente, será necessário customizar a imagem.</h1>

# Há duas formas de criar imagens customizadas: com commit e com Dockerfile.

### Criando imagens com commit

Primeiro criamos um container qualquer
EX:
```bash
docker container run -it --name containercriado ubuntu:16.04 bash
```

Agora paramos o mesmo
EX:
```bash
docker container stop containercriado
```

Agora, efetuamos o commit desse container em uma imagem:
EX:
```bash
docker container commit containercriado meuubuntu:nginx
```
Vamos destrinchar os passos: *containercriado* é o nome do nosso container que criamos *meuubuntu:nginx* é a imagem resultante do commit, o estado do *containercriado* é armazenado em uma imagem chamada *meuubuntu:nginx*. Para vizualizar a lista de imagens usamos o comando.
```bash
dockr image list ou docker image ls.
```

### Criando imagens com Dockerfile
Utilizando o Dockerfile é basicamente uma lista de instruções que serão aplicadas em determinada imagem para que outra imagem seja gerada com base nas modificações.

Primeiro criamos um arquivo 
```bash
touch arquivo_teste
```
Crie um arquivo chamado Dockerfile e dentro dele o seguinte conteúdo:
```bash
FROM ubuntu:16.04
RUN apt-get update && apt-get install nginx -y
COPY arquivo_teste /tmp/arquivo_teste
CMD bash
```
No arquivo acima, utilizamos quatro instruções:

FROM para informar qual imagem usaremos como base, nesse caso foi ubuntu:16.04.

RUN para informar quais comandos serão executados nesse ambiente para efetuar as mudanças necessárias na infraestrutura do sistema. São como comandos executados no shell do ambiente, igual ao modelo por commit, mas nesse caso foi efetuado automaticamente e, é completamente rastreável, já que esse Dockerfile será armazenado no sistema de controle de versão.

COPY é usado para copiar arquivos da estação onde está executando a construção para dentro da imagem. Usamos um arquivo de teste apenas para exemplificar essa possibilidade, mas essa instrução é muito utilizada para enviar arquivos de configuração de ambiente e códigos para serem executados em serviços de aplicação.

CMD para informar qual comando será executado por padrão, caso nenhum seja informado na inicialização de um container a partir dessa imagem. No exemplo, colocamos o comando bash, se essa imagem for usada para iniciar um container e não informamos o comando, ele executará o bash.

Após construir seu Dockerfile basta executar o comando abaixo:
```bash
docker image build -t meuubuntu:nginx_auto .
```
Tal comando tem a opção “-t”, serve para informar o nome da imagem a ser criada. No caso, será meuubuntu:nginx_auto e o “.” ao final, informa qual contexto deve ser usado nessa construção de imagem. Todos os arquivos da pasta atual serão enviados para o serviço do docker e apenas eles podem ser usados para manipulações do Dockerfile (exemplo do uso do COPY).





## Layered File System
<h1>O sistema de arquivos do Docker é chamado de layered, ou seja, é um sistema de arquivo em camadas.</h1>

Nas palavras do próprio Jérome Petazzoni:
Em tradução livre, "seria como se você tivesse um livro e que fosse permitido fazer anotações nele caso quisesse, porém, cada vez que você estivesse prestes a tocar a página com a caneta, de repente alguém aparecesse, tirasse uma xerox dessa página e entregasse a cópia para você. É exatamente assim que o Copy-On-Write funciona".

```bash
# Comando bora billldar
#flag -f: nome do dockfile
#flag -t: Nome que vai ser dado a pessoa que está criando/nome da imagem

docker build -f [nome dockerfile] -t [nome da imagem] .
```