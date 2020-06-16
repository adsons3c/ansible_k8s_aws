# Provisionando, Configurando e Deployando com Ansible 

Este é um exemplo simples de como fazer provisionamneto de instancias EC2, como também configuração e deploy de apps usando o Ansible.  

# Provisioning
Nesta parte do projeto faremos a criação de um security group, das instancias e pegamos os IPs públicos e privados das máquinas e colocamos no arquivo hosts.
Faremos a criação de dois tipos de máquinas, uma mais robusta, para ser nosso server e outras duas mais simples para serem nossos workers.
Usamos bastante o recurso das variáveis, onde neste caso, usamos para:  

  - Indicar o tipo da instancia 
  - O security group 
  - Image
  - Chave
  - Region
  - Quantidade de servers 
  - Quantidade de workers
  - Profile
  - Path do arquivo hosts
```
Para Executar...
$ cd provisioning
$ ansible-playbook -i hosts main.yml
```
# Instalando o K8S

Nesta parte do projeto, iremos rodar as seguintes roles:

  - Install KS8
  - Create Cluster
  - Join workers
  - Install Helm 
  - Install Monit Tools ( Ferramenta de monitoração)
 
```
Para Executar...
$ cd install_k8s
$ ansible-playbook -i hosts main.yml
```

# Deploy APP-v1 e APP-v2
Aqui faremos o deploy de duas versões de um app, isso vai permitir simularmos um upgrade sem down time. 

```
Para Executar...
$ cd deploy-app-v1
$ ansible-playbook -i hosts main.yml
```
```
Para Executar...
$ cd deploy-app-v2
$ ansible-playbook -i hosts main.yml
```

