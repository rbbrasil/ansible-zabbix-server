# Ansible playbook to setup a Zabbix Server
Ansible playbook to install a Zabbix Server instance from source code.

## Requirements
- RHEL/CentOS 7+ distro
- Zabbix tarball package in ``files/`` dir
- Adjust the ``{{ zbx_tar_filename }}`` var in ``vars/main.yml`` to match the Zabbix tarball package filename (**without** extension)

## Usage
```
$ echo my-zbx-srv >> /etc/ansible/hosts
$ ansible-playbook -e hosts=my-zbx-srv main.yml
```

## Before start
You **must** adjust the ``vars/main.yml`` to your environment. There you can modify the usernames, database names, passwords, paths, and others stuffs.

## File structure
The contents of your directory should be like this:

```
ansible-zabbix-server/
├── files/
│   ├── etc_my.cnf
│   ├── etc_php.d_zabbix.ini
│   └── zabbix-3.0.0.tar.gz
├── main.yml
├── README.md
├── tasks/
│   ├── frontend.yml
│   ├── mysql.yml
│   └── startup-scripts.yml
├── templates/
│   ├── root_.my.cnf.j2
│   ├── zabbix_agentd.conf.j2
│   ├── zabbix-agentd.service.j2
│   ├── zabbix.conf.php.j2
│   ├── zabbix_server.conf.j2
│   └── zabbix-server.service.j2
└── vars/
    └── main.yml
```
