## Roles

command to create role  
```
ansible-galaxy role init <role_name>
```
Above command will create below director structure

Directory structure  
```
<role_name>/
  ├── defaults/
  │   └── main.yml
  ├── files/
  ├── handlers/
  │   └── main.yml
  ├── meta/
  │   └── main.yml
  ├── tasks/
  │   └── main.yml
  ├── templates/
  ├── vars/
      └── main.yml
```

Update the main.yml file in tasks folder

```
- name: Install nginx
  ansible.builtin.apt:
      name: nginx
      state: present
      update_cache: yes
```

Create a play-book

```
- hosts: all
  remote_user: adminabdul
  become: yes
  become_user: root
  roles:
    - nginx
```

Create iniventory file

```
[jenkins]
13.93.156.148 ansible_user=adminabdul ansible_ssh_private_key_file=~/.ssh/id_rsa ansible_port=22
```
