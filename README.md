## Задание выполнялось с помощью Ansible [core 2.17.9]

# Порядок выполнения
Необходимо создать rsa ключи с именами (id_rsa id_rsa.pub) в .ssh

### Первые 3 пункта задания  
```bash
ansible-playbook -i inventory.ini setup-ssh.yml
```
### Весь 4 пункт  
```bash
ansible-playbook -i inventory.ini postgres-setup.yml
```
### 5 пункт задания  
```bash
ansible-playbook -i inventory.ini nginx-setup.yml
```
### 6 пункт задания  
```bash
ansible-playbook -i inventory.ini access-setup.yml
```
### 7 пункт задания  
```bash
ansible-playbook -i inventory.ini backup-setup.yml
```
## Особенности  
inventory файл дожен содержать следующие имена хостов  
```bash
hostA.renue 
hostB.renue  
```
Также ip должен указываться в параметре с названием  
```bash
ansible_host  
```
Используется Postgres 16  

при первом запуске, если в known hosts не добавлены хосты, то запустить, ответить yes, перезапустить и ещё раз yes