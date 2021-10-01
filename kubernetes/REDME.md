Laboratório kubernetes

## Comandos
1) Criação de imagem ubuntu
    docker image build -t ubuntu-curl-file .

2) Criando conteiner de app node
    conversao-temperatura
    docker image build -t conversao-temperatura .
    docker container run -d -p 8080:8080 conversao-temperatura

3) Nomeando sua imagem docker padrão
    ezequiel-cruz/api-conversao-temperatura:v1
    docker image build -t ezequiel-cruz/api-conversao-temperatura:v1 .
    docker container run -d -p 8080:8080 ezequiel-cruz/api-conversao-temperatura:v1

4) Diferença de entrypoint e cmd
    docker image build -t ezequiel-cruz/ubuntu-start:cmd .
    docker container run -d -p 8080:8080 ezequiel-cruz/ubuntu-start:cmd

    docker container run ezequiel-cruz/ubuntu-start:entry .
    docker container run -d -p 8080:8080 ezequiel-cruz/ubuntu-start:entry 

5) Usando argumentos
    docker image build -t ezequiel-cruz/ubuntu-arg:v1 --build-arg TAG="18.04" .
    docker container run -d -p 8080:8080 ezequiel-cruz/ubuntu-arg:v1

6) Criando image multistage Build
   docker image build -t ezequiel-cruz/go-app:simples .
   docker container run -d -p 8080:8080 ezequiel-cruz/go-app:simples

7) Docker Registry
   1) Docker Hub
   2) Elastic Container Registry
   3) Azure Container Registry
   4) Google Container Registry
   5) Harbor
    
