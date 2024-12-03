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


## Cluster Kubernetes em produção

Componentes da camada de gerenciamento:
- kube-apiserver - atende as operações e fornece o frontend para o estado compartilhado do cluster;
- etcd - amazenamento principal de dados do Kubernetes;
- kube-scheduler - atribui pods aos nós;
- kube-controller-manager - controlador que observa o estado compartilhado do cluster e faz alterações tentando mover o estado atual para o estado desejado.

Acesse o site https://aws.amazon.com/pt/cli/ para baixar e instalar a interface de linha de comando da AWS. Procure pela versão compatível com seu sistema operacional.

![D2 01](https://github.com/user-attachments/assets/640a6fab-9b69-4ec5-874b-d2e0ad07768e)

Após a instalação, abra o terminal (por exemplo o PowerShell) e digite o comando abaixo:

![D2 02](https://github.com/user-attachments/assets/4db367b9-f2c7-4f6a-9a01-2d5f70f9957c)

No portal da AWS pesquise por IAM para encontrar sua credencial/chave de acesso a ser utilizada para estabelecer a conexão do terminal com a nuvem.

No terminal digite o comando *aws configure* e informe o AWS Access Key ID e o AWS Secret Access Key, os demais parâmetros não são obrigatórios.

![D2 03](https://github.com/user-attachments/assets/223bdf1d-40e4-49a5-a8e7-b97833e3bda9)


## Criação do cluster utilizando AKS

No portal da AWS procure por Elastic Kubernetes Service, cuidando para que a região utilizada seja a mesma do Cluster já criado e clique em Add Cluster para criar, pode-se manter as configurações padrões preenchendo apenas o que for necessário.

![D2 04](https://github.com/user-attachments/assets/846b4af2-ded2-4bba-af55-c82212483c99)

Digite o comando abaixo para verificar o status do cluster EKS criado:

![D2 05](https://github.com/user-attachments/assets/8ec9727d-bf17-47da-82c0-9a39d45110b0)

Execute o comando abaixo para fazer o upload do cluster para a máquina local:

![D2 06](https://github.com/user-attachments/assets/bf022512-008e-415d-bd9a-862b85086e8a)

Digite o comando abaixo para verificar o status, IP e demais informações do cluster criado:

![D2 07](https://github.com/user-attachments/assets/89ca1a93-f460-478e-999e-2c474386966b)


## Adiconando nodes ao Cluster

No portal da AWS acesse o cluster criado e vá para a aba Compute para criar os nós, clicando em *Add node group*:

![D2 08](https://github.com/user-attachments/assets/123b9c99-db23-40b8-b81d-72e49c7603d0)

Adicione as três políticas abaixo no momento da criação dos nodes:

![D2 09](https://github.com/user-attachments/assets/6e42e509-6234-4086-9683-f7358fdff061)

O comando abaixo verifica o status da criação de cada nó:

![D2 10](https://github.com/user-attachments/assets/cfbbc577-d2b4-4921-8501-d385dae4de64)

![D2 11](https://github.com/user-attachments/assets/65722922-9bc6-43a5-825e-ef4848618239)


## Criando um cluster em nuvem utilizando GCP

Caso opte por utilizar o Google Cloud Platform, após criar o cluster e os nós no portal, e realizar o download da interface de linha de comando da GCP devem ser executados os seguintes comandos no terminal:

![D2 12](https://github.com/user-attachments/assets/443265e6-ae34-4e92-88fd-fa58cdb78743)

Utilize o comando abaixo para logar no ambiente de cloud a partir do terminal:

![D2 13](https://github.com/user-attachments/assets/8ec5e569-f598-4d69-ad34-ad0604cfe785)

O comando abaixo mostra o usuário que está autorizado a realizar a conexão:

![D2 14](https://github.com/user-attachments/assets/5b818e45-db72-43ae-be40-e245c4fb0706)

Para se conectar ao cluster a partir do terminal, acesse a platarforma do GCP, localize o cluster criado e clique em **Conectar**:

![D2 15](https://github.com/user-attachments/assets/b81d612a-8391-42ed-ac9c-206d850319cc)

Copie a linha de comando informada e execute no terminal, execute também o comando *kubectl.exe get nodes* para verificar os nós criados:

![D2 16](https://github.com/user-attachments/assets/7c569d07-9894-44a9-a876-190282b129cd)


