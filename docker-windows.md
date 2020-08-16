# linux

## REALIZAR TODAS AS ALTERAÇÕES DO WINDOWS ANTES (UPDATE)

https://www.youtube.com/watch?v=g4HKttouVxA&feature=youtu.be

https://github.com/codeedu/wsl2-docker-quickstart


## Resumo

### Executar no terminal do Windows como administrador
```properties
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
```properties
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

> Atualizar o kernel do WSL 2 Linux
https://docs.microsoft.com/pt-br/windows/wsl/wsl2-kernel

> Atribua a versão default do WSL para a versão 2
```properties
wsl --set-default-version 2
```

> Escolha sua distribuição Linux no Windows Store

> *Ao iniciar o Linux instalado, você deverá criar um nome de usuário que poderá ser o mesmo da sua máquina e uma senha, este será o usuário root da sua instância WSL.*

> Se você já tiver o WSL 1 na máquina e acabou de instalar a versão 2, pode-se converter sua distribuição Linux WSL 1 para WSL 2, execute o comando com o PowerShell:
```properties
wsl --set-version "ubuntu" 2
```

> Use Windows Store para instalar Windows Terminal como terminal padrão de desenvolvimento para Windows
> Para sobrescrever as configurações clique a seta para baixo do lado das abas e em configurações, abrirá as configurações do Windows Terminal, apenas cole o conteúdo do arquivo JSON e salve.
Configurações: https://github.com/codeedu/wsl2-docker-quickstart/blob/master/windows-terminal-settings.json

> Integrar Docker com WSL 2 (apenas instalar e avançar)
https://hub.docker.com/editions/community/docker-ce-desktop-windows

> Habilite o Docker dentro do WSL 2
Clique no ícone do Docker perto do relógio -> Settings -> Settings no topo -> Resources -> WSL Integration.

Habilite Enable integration with my default WSL distro e habilite sua versão Linux.

> Use BuildKit and multi-stage builds
Acrescente export DOCKER_BUILDKIT=1 no final do arquivo .profile do seu usuário do Linux para ganhar mais performance ao realizar builds com Docker. Execute o comando source ~/.profile para carregar esta variável de ambiente no ambiente do seu WSL 2.

> Habilitar no VSCode o plugin Remote WSL

```Instlar Windows Terminal
wsl --set-version "ubuntu" 2
```






- ### Intalação [docker](https://www.docker.com)

1. Download [DockerToolbox](https://docs.docker.com/toolbox/toolbox_install_windows/)
1. [x] Help Docker imporove Toolbox.
1. Next > Next > Next...
1. [x] View Shortcuts in File Explorer
1. Menu do Windows > Docker
1. Open Docker Quickstart Terminal (aguardar carregar)
1. Open Kitematic > Use Virtualbox > Login


https://docs.docker.com/toolbox/toolbox_install_windows/
https://www.youtube.com/watch?v=2Rc7glcM3D8
