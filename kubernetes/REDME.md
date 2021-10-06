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

8) Kubernetes formas de cluster
   1) On_Premisse
      1) Kubeadm
      2) Kubespray
      3) RKE
      4) K3S
      5) MicroK85
   2) Kubernetes as a Service
      1) AKS - Azure
      2) EKS - AWS
      3) GKS - Google
      4) OKE - Oracle
   3) Local
      1) Minikube
      2) Kind
      3) K3D
      4) MicroK8S *
      5) K3S *

9) Kind - Kubernetes In Docker
   1)  Instalação do Kubectl
     https://kind.sigs.k8s.io/docs/user/quick-start/#installation
     https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/

10) Criação do cluster
    kind create cluster
    kind create cluster --name meucluster

    kubectl get nodes
    kind get clusters
    kind delete cluster

11) Usando arquivo config
    kind create cluster --name meucluster -- config cluster.yaml

12) Criando Pod
    kubectl create -f meupod.yaml (apply)
    kubectl get pods
    kubectl describe pod meupod

    kubectl port-forward pod/meupod 8080:80
    kubectl delete pod meupod
