# ansible-vmware

Criação de vms no vCenter com infra como código usando o ansible.

# Pré requisitos

Instalar o ansible

https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

Instalar o pip do python para instalar a API de conexão com o vCenter.

```
sudo apt install python-pip
sudo pip install pyvmomi
```
# 1 Criar o arquivo com usuário e senha
```
sudo vim /etc/ansible/group_vars/vcenter-vars.yml
```
Encripitar essas informções. Vai pedir para definir uma senha, pode ser qualquer uma, ela será pedida na exeção do playbook.
```
sudo ansible-vault encrypt /etc/ansible/group_vars/vcenter-vars.yml
```

# 2 Criar o playbook que será executado

```
sudo vim /etc/ansible/playbooks/vcenter-vm.yml
```

# 3 Executar  o playbook
```
sudo ansible-playbook /etc/ansible/playbooks/vcenter-vm.yml --ask-vault-pass -K
```
