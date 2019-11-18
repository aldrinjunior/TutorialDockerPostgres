# TutorialDockerPostgres
Fala galera ! No tutorial de hoje vamos entender o que é docker, e como instalar ele na sua maquina !

Primeiramente, vamos entender que o docker não é um serviço de virtualização comum como um virtualbox da vida, ele é um sistema que utiliza containers, e dentro desse container, ele possui o mínimo nescessário de uma distro linux para rodar a imagem isolada de uma aplicação que você deseja. Nesse caso aqui, vamos aprender a instalar e utilizar o banco Postgres.

Eu sugirio que instalem o docker no Linux, nunca utilizei ele nativamente no windows devido alguns bug que nós já conhecemos, mas se quiserem tentar podem conferir a instalação no link abaixo

LINK DOCKER WINDOWS : https://docs.docker.com/docker-for-windows/install/

Mas para quem não quer criar um dual boot ou deixar de usar o windows, pode baixar a versão do Ubuntu WSL na própia loja da Microsoft e desfrutar dessa distro dentro do windows sem complicações, segue o tutorial de instalação abaixo : 

Link WSL instalation : https://docs.microsoft.com/en-us/windows/wsl/install-win10

(IMPORTANTE: Precisa ter a versão do Windows 10 atualizada acima da build 1903, se caso não funcionar a instalação acima é só ir nas configs do windows e atualizar, mesmo sendo piratão hehhehhehe)

Após instalar o WSL dentro do windows, vamos instalar o docker dentro do WSL 

(Para quem já tem linux é só abrir o terminal e rodar o comando abaixo)

sudo apt install docker.io

============================================================================================================

Depois do docker instalado, precisamos baixar o container que vamos utilizar, nesse caso do postres, é só rodar o comando abaixo, mas para baixar outras imagens, exemplo : NodeJS, MongoDB, .net, java, MySQL, é só pesquisar elas dentro do site https://hub.docker.com/

docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres

============================================================================================================

Após rodar esse comando, ele vai fazer o download do postgres versão 11, lembrando que vocês podem mudar a versão e também rodar o comando outras vezes com outras versões caso precise instalar um postgres mais antigo para dar manutenção em um projeto que já estava pronto.

============================================================================================================
Para listar as imagens instaladas no Docker, é só abrir o terminal e rodar:

docker ps -a

E depois para rodar uma imagem :

docker start nomedocontainer

============================================================================================================

Agora vamos rodar essa imagem postgres dentro de um projeto da aula, vamos abrir o VSCODE, e na appsettings.json é só criar a string de conexão com as credenciais utitlizadas ali no comando do docker run, que neste caso do tutorial é :

name : some-postgres
PASSWORD=mysecretpasswor

