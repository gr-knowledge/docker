docker pull nginx (baixar imagem)
docker container run <container> (roda um container)
docker container rm <id1> <id2> <...>
docker container start <id | name> (inicia container)
docker container top <id> (mostra processos do container)
docker container inspect <id> (mostra detalhes da configuração)
docker container stats (mostra consumo dos containers)


docker images

docker container run --publish 8080:80 nginx
docker container run --publish 8080:80 --detach nginx
docker container run --publish 8080:80 --detach --name meuTeste nginx


docker container run -it ubuntu (roda container com interação no terminal)
docker container attach <id> (volta a utilizar terminal do container)
exit (sair o terminal do container)


--publish 8080:80 (mapear porta)
-P (mapeia para qualquer porta aleatória para evitar conflito de porta)
--detach (rodar em background)
--name (especifica nome ao container)
--interactive (poder digitar comandos no terminal do container)







# Docker Command Line
docker container --help (ajuda específica)
docker <command> <sub command> (options)

docker (lista de comandos)
docker container ls (lista containers em execução)
docker container ls --all (lista containers em execução ou não)
docker version
docker info
docker container stop <id | name>

docker container exe ID ls -ls (roda um comando dentro do continer)
docker container rename ID novoNome
docker container prune (remove todos containers inclusive parados)
docker 
docker 




*** IMAGE ***
docker rmi image01 image 02 (remove images)


*** AWS CLOUD 9 *** (ambiente para rodar projetos online)
// https://hub.docker.com/r/sapk/cloud9
docker pull sapk/cloud9
docker run -d -v $(pwd):/workspace -p 8182:8181 sapk/cloud9 --auth user:1
docker run -d -v $(pwd):/workspace -p 8181:8181 -p 4200:4200 sapk/cloud9 --auth user:1
docker run -d  -p 8181:8181 sapk/cloud9 --auth username:password

docker image inspect ID
"": {
  "/workspace": {}
},

docker volume ls
docker volume rm ID (remove colume)
docker volume inspect HASH

*** VOLUME / WORKSPACE *** (sincronizar arquivos e pastas com pc)




*********** LINUX **************
pwd (no linux é o caminho atual do prompt no terminal)
toutch teste.txt (criar arquivo)



**************************************************
*
* CURL | COMMIT | NVM (Gerenciador de versões do Node.js)
*
**************************************************
apt-get install curl
https://github.com/nvm-sh/nvm (documentação nvm)
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash (instalação do nvm)
$ command -v nvm (mostra versão)
$ source ~/.bashrc (carregar terminal após instalação)
$ nvm ls (mostra versões do node instaladas e default)
$ nvm ls-remote (lista versões disponíveis do node no servidor)
$ nvm install 10.21.0 (instala versão específica do node)
$ nvm current (mostra versão atual, mesmo que o node -v)
$ nvm use 12.9.1 (alterna entre as versões instaladas)
$ docker container commit -m "Adicionado NVM e curl" ID (adiciona a imagem local as alterações realizadas, sendo aplicada não somente no container atual, mas nos novos também.)
$ docker run -d -v $(pwd):/workspace -p 8181:8181 -p 4200:4200 ID --auth user:1 (roda imagem local com commit adicionado)

$ docker image history ID (mostra o histórico da image/commit)



**************************************************
*
* SSH
*
**************************************************
$ docker pull rastasheep/ubuntu-sshd
$ docker images (pegue ID da nova imagem)
$ docker container inspect ID (pegar porta em ExposedPort)
$ docker image inspect --format '{{.Config.ExposedPorts}}' ID (filtra o resultado)
$ dockerl container run -d -P ID (roda container, -P deixa ele se virar para mapear porta)
$ docker port ID (mostra para qual porta foi mapeado)
$ docker port ID 22 (informar a porta é opcional, pode existir várias portas mapeadas)
Acessar SSH com Windows: www.gitforwindows.org (utilizar o prompt que foi instaladol)
Via terminal: 
  $ ssh root@localhost -p 32794
  password: root


********** RODANDO IMAGEM CRIADA COM NVM E COMMIT ********
$ docker run -d -v $(pwd):/workspace -p 8181:8181 -p 3000:3000 {ID_NVM_COMMIT} --auth user:1
Inicar server no CLOUD9 via browser
$ docker container stop ID (parar container)
$ docker run -d -v $(pwd):/root -P -p 3000:3000 {ID_NVM_COMMIT} --auth user:1 (root para ir para raiz do usuário)
$ docker port ID
$ ssh root@localhost -p 32794
(... FALTA FINALIZAR A AULA... )

PAREI NA AULA 19 SERVIDOR HTTP
