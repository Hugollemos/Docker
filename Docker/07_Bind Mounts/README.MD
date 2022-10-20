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