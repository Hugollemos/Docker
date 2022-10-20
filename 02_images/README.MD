# Images
<h1>Fazendo uma analogia com POO "A classe representa a imagem enquanto sua instância, o objeto, é o contêiner. A mesma imagem pode criar mais contêineres."</h1>

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