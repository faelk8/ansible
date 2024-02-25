


Provisiona com o Terraform
Configurações com Ansible

hosts 
Arquivo de inventário
Todos os IPs de todas as máquina para executar comandos

# Testando conexão
```
ansible -i hosts all -m ping
```

# Playbook
```
ansible-playbook -i playbook.yaml
```

# Instalando Nginx
Criando regras para o serviço, isso ajuda a separ.
```
ansible-galaxy init install_nginx
```

Cria pastas para para orgazinar as tarefas e serviços relacionados ao nginx. Mais utilizados:
* files
* handlers
* tasks
* templates
* vars

Na pasta **tasks** foi configurado para instalar e inicar o nginx.<br>

# Instalando Docker
Docker
```
ansible-galaxy init install_docker
```
Ajuste a regras do task para instalação do Docker.

# Docker Swarm

```
ansible-galaxy init docker_swarm_manager
```
Separando o host em:
* Manager
* Worker

```
ansible-galaxy init docker_swarm_worker
```

# Deploy
Colocando em produção

```
ansible-galaxy init deploy_stack 
```

# Iniciando o serviço

Para iniciar todo o serviço criar `main.yaml` que faz a chamada de todos os pacotes.
```
ansible-playbook -i ../hosts main.yaml
```
