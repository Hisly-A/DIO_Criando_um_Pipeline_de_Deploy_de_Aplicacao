# DIO - Criando um Pipeline de Deploy de uma Aplicação
 Criando um Pipeline de Deploy de uma Aplicação Utilizando Gitlab, Docker e Kubernetes


## Instalação do minikube

Inicialmente iremos utilizar o minikube, um utilitário para executar o Kubernetes na máquina local criada no VirtualBox.

Acesse o site oficial do minikube https://minikube.sigs.k8s.io/docs/start/, realize o download da versão compatível com seu sistema operacional e faça a instalação.

No terminal execute o comando do minikube para iniciar o cluster:
- minikube start

Esse comando irá criar automaticamente uma máquina virtual no VirtualBox já com o Linux e Docker.

Com o comando *minikube status* é possível ver o status dos seus serviços.

Com o comando *minikube stop* é possível parar/desligar o cluster. E com o comando *minikube start* reiniciá-lo.


## Instalando o kubectl

Essa é a ferramenta de linha de comando do Kubernetes.

Para realizar o download acesse o site do Kubernetes https://kubernetes.io/docs/tasks/tools/

Localize os comandos de instalação específicos para o sistema operacional utlizado na sua máquina. Por exemplo, para Windows é realizado o download de um arquivo exz.

Ainda no Windows acesse as variáveis de ambiente e em Path adicione o caminho de onde se encontra o arquivo exz baixado, isso será necessário para permitir que o arquivo seja aberto de qualquer lugar de sua máquina.


