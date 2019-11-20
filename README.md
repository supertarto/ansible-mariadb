# Ansible MariaDB
Install and configure MaraiDB with Ansible

## Requirements
None

## Tested plateform
* Debian 9 (Stretch)
* Debian 10 (Buster)

## Role variables


## Examples
```yml
- hosts: somehost
  roles:
    - role: supertarto.mariadb

  vars:
    mariadb_use_dump_script: true

    mariadb_databases:
      - name: database1
        collation: utf8_general_ci
        encoding: utf8

    mariadb_users: []
      - name: username
        host: localhost
        password: sqlpassword
        priv: "database1.*:SELECT,UPDATE"

      - name: "{{ mariadb_dump_user }}"
        host: localhost
        password: "{{ mariadb_dump_pass }}"
        priv: "*.*:SELECT,LOCK TABLES"   
 
    mariadb_dump_user: "dumpuser"
    mariadb_dump_pass: "Dumppassword"
```
## Installation
```
ansible-galaxy install supertarto.mariadb
```
## License
GPL V3.0
