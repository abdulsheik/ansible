## Command to run the ansible-playbook

```
ansible-playbook <playboom.yaml>
```

## playbook-test.yaml

```
---
- hosts: all
  remote_user: adminabdul
  become: yes
  become_user: root
  tasks:
    - name: Install apache httpd
      ansible.builtin.apt:
        name: apache2
        state: present
        update_cache: yes
```

- ```hosts: all``` [refers to the hosts in inventory file]
- remote_user: adminabdul [user to login remote hosts using SSH]
- becomes: yes [adminabdul user gains sudo privileges]
- become_user: root [root user to install any packages]


abdul notes  
new notes
