## Задание выполнялось с помощью Ansible [core 2.17.9]

# Порядок выполнения
Необходимо создать rsa ключи с именами (id_rsa id_rsa.pub) в .ssh

### Отключение авторизации по паролю через SSH на обоих серверах. Добавление пользователя DevOps и настройка sudo без пароля на обоих серверах. Настройка fail2ban на сервере А  
```bash
ansible-playbook -i inventory.ini setup-ssh.yml
```
### Установка PosthgreSQL на сервере А  
## Добавление пользователя app с паролем app с полным доступом к БД app  
## Добавление пользователя custom с паролем custom с полным доступом к БД custom  
## Добавление пользователя service с паролем service c паролем app с полным доступом на чтение к обоим БД  
```bash
ansible-playbook -i inventory.ini postgres-setup.yml
```
### Установка nginxна сервере Б и настроить его так, чтобы при обращении на
сервере к localhost (или его доменному имени) открывался сайт https://renue.ru   
```bash
ansible-playbook -i inventory.ini nginx-setup.yml
```
### Настройка доступа к PostgreSQL на сервере А только с сервера Б, закрыть доступ к
nginx на сервере Б с сервера А     
```bash
ansible-playbook -i inventory.ini access-setup.yml
```
### Настройка бэкапирования PostgreSQL с сервера А на сервер Б    
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
