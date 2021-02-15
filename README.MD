# O Laboratorio e exercicio foram criado na AWS

# Deploy Automatizado via AWS Cloud Formation #

1. Efetue o Uploado do arquivo MyInstance-v2 e siga o Wizard ( Zona / Tipo de Instancia )
OBS. Esse template esta customizado para recebar a Subnet / VPC padrão e a imagem do Ubuntu

# Instalação automatizada do Docker e Criação de um container com a Imagem do apache #

2. Subentendo que o ambiente possua um servidor com ubuntu + ansible
2.1 Efetue o Uploado da Estrutura Docker.zip para a pasta /tmp/
2.2 Faça o unzip do Pacotes para o patch /etc/ansible/
2.3 Edit o arquivo host e adicione o IP / FQDN no servidor criado no Step 01 no Grupo servers
2.3 Execute o comando ansible-playbook playbook.yaml

OBS: Esse playbook efetuará a instalação dos Pacotes do Docker e criará um container com a imagem do apache escutando na Porta 8080 o mesmo poderá ser acessado atraves do IP Publico

# Atualização dos Binarios da Aplicação #

1. Por Padrão a aplicação mostrará um pagina Padrão, mas para fazer a substituição da mesma basta executar o playbook update-app-yaml
1.1 Execute o comando ansible-playbook update-app-yaml

OBS:. Necessario atualizar o path /tmp/ com o novo arquivo .. nesse exemplo estou apenas substituindo a pagina index.html 

Nesse exercicio utilizei as Produtos: ( AWS Cloud Formation \ Ansible \ Docker ), porem em outros cenarios e possivel utilizar o Terraform ( Provisionar ) + Ansible e EKS ( Cluster Kubernete ) para o orquestração dos container, eliminando o ponto de falha em caso disaster.

Para update da aplicação e possivel utilizar o Jenkins ou o Chef para automatizar as publicações
