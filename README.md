# Ansible Role FE2

Ansible Role zur Installation von Alamos FE2 auf Linux servern. Getestet auf Debian und Ubuntu. 

## Download


```bash
cd /etc/ansible/roles
mkdir fe2 && cd fe2
git clone https://github.com/Finn0811/Ansible-Role-FE2.git
```



## Usage
### Create fe2 playbook
`nano /etc/ansible/fe2.yml`

```yml
- name: install fe2 server on linux servers
  hosts: fe2
  remote_user: root

  roles:
    - fe2
```

### Create `fe2_download_url` group var to use for all fe2 hosts
`nano /etc/ansible/group_vars/fe2.yml`

```yml
fe2_download_url: http://files.alamos-gmbh.com/FE2/stable/FE2-2.21.116.zip
```

### Add host
`nano /etc/ansible/hosts`

```
[fe2]
192.168.178.112 alamos_email="user@name.com" alamos_password="pass1word" public_ip="192.168.178.112"
```

## Run playbook
`ansible-playbook /etc/ansible/fe2.yml`
