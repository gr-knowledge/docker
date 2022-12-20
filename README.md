# docker

https://docs.docker.com/toolbox/toolbox_install_windows/

Se Windows não for compatível, instalar o Docker Toolbox para criar uma máquina virtual.

Durante a instalação aceitar um "dispositivo USB"

### Abrir o atalho
> Docker Quickstart Terminal (terminal para comandos).
> ***Se utilizar outro terminal não irá funcionar.***

### Testar se docker está instalado
```propertier
docker
```

## Docker container

| Comando | Descritivo |
|-|-|
| container ls | Lista containes ativos |
| container ls -a | Lista containes que estão rodando e parados|
| container ps | Lista containes ativos |
| container ps -a | Lista containes ativos ou parados|
| container run --name my-container | Executa container |
| container start my-container | Inicia container |
| container start -ai my-container | Inicia container com acesso ao terminal |
| container stop my-container | Para container |
| container restart my-container | Reiniciar container |
| container logs my-container | Mostra logs|
| container inspect my-container | Informações detalhadas sobre o container |
| container exec my-container uname -or| Executa comando no contairner |
| container rm my-container | Remove container |

## Docker image
| Comando | Descritivo |
|-|-|
| container ls | Lista container |
| image ls | Lista imagens |
| image rm | remove imagem |
| volume ls | Lista volumes |

## Sinalizadores
| Sinalizador | Descritivo |
|-|-|
| --name my-container | Nomear |
| -p 8080:80 |Portas |
| -v $(pwd)/html:/usr/share/nginx/html | Volume |
| volume ls | Lista volumes |
| -d | Container em backuground |
| --rm | Remove o container após ser executado |
| -it | Acesso ao terminal do container ao ser criado (run) |
| -ai | Acesso ao terminal do container ao ser inicializado (start) | 


# Comandos linux
| Comando | Descritivo |
|-|-|
| touch my-file.txt | Cria arquivo |
| mkdir my-folder | Cria Diretório |


### Hello Word  
> Se imagem não existir, irá baixar... Se rodar o comando novamente será mais rápido, já que a imagem já foi baixada.  
> ***Irá exibir no terminal "Hello from Docker!"***
```propertier
docker container run hello-world
```

### Comando Run
> É uma concateção de 4 comandos:
```propertier
\\ baixar imagem
docker image pull

\\ criar imagem
docker container create

\\ inicialização do container
docker container start

\\ execução do container
docker container exec
```

## Modo interativo:


> Lista processos
```propertier
ps
```

> Lista containers criados
```propertier
ls -ai
```

> Lista de container ativos neste momento.
```propertier
docker container ps
```

> Lista de todos container idependente do status.
```propertier
docker container ps -a
```

> Executa container e remove da lsita
```propertier
docker container run --rm hello-world
```

***Sempre que Run é chamado é criado um novo container***

> Entra no terminal do container
```propertier
docker container run -it debian bash
```

> Renomear container e não deixar criar novamente mesmo nome.
```propertier
docker container run --name myTeste hello-world
```


# Aula 22
