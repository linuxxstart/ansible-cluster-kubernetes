# ansible-cluster-kubernetes

Criação de vms no vCenter com infra como código usando o ansible.

# Pré requisitos
Matrix de compatibilidade dos sistemas operacionais das vms
http://partnerweb.vmware.com/programs/guestOS/guest-os-customization-matrix.pdf

Exemplo que estou usando é o ubuntu-18.04

Instalar o ansible

https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

Instalar o pip do python para instalar a API de conexão com o vCenter.

```
sudo apt install python-pip
sudo pip install pyvmomi
```
# 1 Criando variáveis

Depois de clonar o repositório edite o arquivo.
```
$ vim group_vars/all
```
Encripitar essas informções. Vai pedir para definir uma senha, pode ser qualquer uma, ela será pedida na exeção do playbook.
```
$ ansible-vault encrypt group_vars/all
```

# 2 Edite infos que precisar nos arquivos abaixo

```
$ vim vms_deploy
$ vim main.yml
$ vim roles/vms/tasks/main.yml
$ vim roles/master/tasks/main.yml
$ vim roles/worker/tasks/main.yml
```

# 3 Executar  o playbook
```
$ ansible-playbook -i vms_deploy main.yml --ask-vault-pass -K
```

# Fontes

https://github.com/learnitguide/kubernetes-and-ansible
https://kubernetes.io/blog/2019/03/15/kubernetes-setup-using-ansible-and-vagrant/

