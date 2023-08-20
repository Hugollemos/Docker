###  criar máquina
```
docker-machine create --driver virtualbox [nome da máquina] 
```
### Listar as máquina
```
docker-machine ls
```
### Visualizar informações sobre o host
```
docker-machine env linuxtips
```
#### Verificar o ip do host 
```
docker-machine ip [nome da maquina]
```
### Detalhes sobre o host
```
 docker-machine inspect linuxtips
```
SAÍDA ESPERADA
 ``` 
 {
    "ConfigVersion": 3,
    "Driver": {
        "IPAddress": "192.168.99.100",
        "MachineName": "HUGO",
        "SSHUser": "docker",
        "SSHPort": 57249,
        "SSHKeyPath": "/Users/jeferson/.docker/machine/machines/VM/id_rsa",
        "StorePath": "/Users/jeferson/.docker/machine",
        "SwarmMaster": false,
        "SwarmHost": "tcp://0.0.0.0:3376",
        "SwarmDiscovery": "",
        "VBoxManager": {},
        "HostInterfaces": {},
        "CPU": 1,
        "Memory": 1024,
        "DiskSize": 20000,
        "NatNicType": "82540EM",
        "Boot2DockerURL": "",
        "Boot2DockerImportVM": "",
        "HostDNSResolver": false,
        "HostOnlyCIDR": "192.168.99.1/24",
        "HostOnlyNicType": "82540EM",
        "HostOnlyPromiscMode": "deny",
        "UIType": "headless",
        "HostOnlyNoDHCP": false,
        "NoShare": false,
        "DNSProxy": true,
        "NoVTXCheck": false,
        "ShareFolder": ""
    },
    "DriverName": "virtualbox",
    "HostOptions": {
        "Driver": "",
        "Memory": 0,
        "Disk": 0,
        "EngineOptions": {
            "ArbitraryFlags": [],
            "Dns": null,
            "GraphDir": "",
            "Env": [],
            "Ipv6": false,
            "InsecureRegistry": [],
            "Labels": [],
            "LogLevel": "",
            "StorageDriver": "",
            "SelinuxEnabled": false,
            "TlsVerify": true,
            "RegistryMirror": [],
            "InstallURL": "https://get.docker.com"
        },
        "SwarmOptions": {
            "IsSwarm": false,
            "Address": "",
            "Discovery": "",
            "Agent": false,
            "Master": false,
            "Host": "tcp://0.0.0.0:3376",
            "Image": "swarm:latest",
            "Strategy": "spread",
            "Heartbeat": 0,
            "Overcommit": 0,
            "ArbitraryFlags": [],
            "ArbitraryJoinFlags": [],
            "Env": null,
            "IsExperimental": false
        },
        "AuthOptions": {
            "CertDir": "/Users/HUGO/.docker/machine/certs",
            "CaCertPath": "/Users/HUGO/.docker/machine/certs/ca.pem",
            "CaPrivateKeyPath": "/Users/HUGO/.docker/machine/certs/ca-key.pem",
            "CaCertRemotePath": "",
            "ServerCertPath": "/Users/HUGO/.docker/machine/machines/VM/server.pem",
            "ServerKeyPath": "/Users/HUGO/.docker/machine/machines/VM/server-key.pem",
            "ClientKeyPath": "/Users/HUGO/.docker/machine/certs/key.pem",
            "ServerCertRemotePath": "",
            "ServerKeyRemotePath": "",
            "ClientCertPath": "/Users/HUGO/.docker/machine/certs/cert.pem",
            "ServerCertSANs": [],
            "StorePath": "/Users/HUGO/.docker/machine/machines/VM"
        }
    },
    "Name": "VM"
}
 ```
### Parando o host:
``````
docker-machine stop vm
``````
### Ver 0 status do host Docker:
``````
docker-machine ls
``````
### iniciá-lo novamente:
``````
docker-machine start VM1
``````
### Para removê-lo definitivamente:
``````
docker-machine rm linuxtips
``````

## Comando para criar a máquina
```
docker-machine create -d virtualbox [nome]
```