# Instalação do Docker no Windows com WSL

Este guia descreve os passos para instalar o Docker no Windows utilizando o **WSL (Windows Subsystem for Linux)** com a distribuição **Ubuntu**.

## O que é o WSL?

O **WSL** é uma funcionalidade do Windows que permite executar um ambiente Linux completo directamente no Windows, sem precisar de máquinas virtuais ou dual boot. Ele traduz chamadas do sistema Linux para o kernel do Windows, proporcionando uma integração eficiente e leve.

## Passos para Instalar o WSL e o Docker

### 1. Instalar o WSL

1. Abra o **PowerShell** como administrador.
2. Execute o seguinte comando para instalar o WSL com o Ubuntu:
  
   wsl --install -d Ubuntu

3. Após a instalação, configure o seu username e password dentro do ambiente Ubuntu.

4. Instalar o Docker

    Acesse o site oficial do Docker e faça o download da versão para Windows:
    Site oficial do Docker
    Siga as instruções de instalação para configurar o Docker no seu sistema. https://www.docker.com/

5. Instalar e Executar Imagens no Docker

    Acesse o Docker Hub https://hub.docker.com/ para procurar imagens de containers.Por exemplo, para instalar uma imagem do MySQL, execute o seguinte comando no PowerShell:

    docker pull mysql

6. Após a instalação da imagem, podes verificar as imagens disponíveis no Docker com o seguinte comando:

      docker images 

7. Para iniciar um container MySQL, execute o seguinte comando:<br>

docker run -d -p 3306:3306 --name mysql_vicente -e MYSQL_ROOT_PASSWORD=123456 mysql:latest

Explicação do Comando:
***********************************************************************************************
    docker run: Cria e inicia um novo container.
    -d: Executa o container em segundo plano (modo "detached").
    -p 3306:3306: Mapeia a porta 3306 do container para a porta 3306 do host, permitindo o acesso ao MySQL.
    --name mysql_vicente: Dá o nome "mysql_vicente" ao container.
    -e MYSQL_ROOT_PASSWORD=123456: Define a palavra-passe de root do MySQL como "123456".
    mysql
    : Utiliza a versão mais recente da imagem do MySQL.
   

8. Para listar todos os containers (em execução ou parados), use o seguinte comando: <br>

   docker ps -a
**********

Considerações Finais

Seguindo estes passos, o Docker estará instalado e funcional no seu sistema Windows através do WSL. 

Caso precise de mais informações consulte a documentação oficial do Docker ou a documentação do WSL.
