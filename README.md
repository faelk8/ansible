


Provisiona com o Terraform
Configurações com Ansible

hosts 
Arquivo de inventário
Todos os IPs de todas as máquina para executar comandos

```
ansible -i hosts all -m ping
```

# Criando um controlador

acessando o control

docker exec -it control bash 

acessando máquina node1
docker exec -it node1 bash 

Inicia o ssh 
service ssh start

Para conectar do contronol no node1 
ssh root@node1

Gerando chave ssh
ssh-keygen

 Copiando a chave para o node1
ssh-copy-id root@node1


Acessar
ssh root@node1

Executar ping dentro do node1 tem que estar na pasta /root/ansible
Informações da máuina
ansible -i hosts all -m shell -a 'uptime'

# Instalando o Git 
ansible -i hosts all -m apt -a "update_cache=yes name=git state=present"

Baixando repositorio para todas as máquinas
ansible -i hosts all -m git -a "repo=https://github.com/faelk8/kubernetes.git dest=/root/kubernetes"


ansible -i hosts all -m apt -a "update_cache=yes name=nginx state=present"

# Remover
ansible -i hosts all -m apt -a "update_cache=yes name=nginx state=absent"