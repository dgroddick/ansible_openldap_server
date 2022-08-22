# OpenLDAP Server Ansible Role

Ansible role for setting up OpenLDAP server.
Tested and working on Enterprise Linux 7. I'll update to work on EL8 as well.

You'll need to change the domain suffix in the files, but I'll do something about that as well.

## Deployment

Assuming you have an Ansible environment set up, clone the repo into your Ansible workspace inside the roles directory:

```
$ cd ansible/roles
$ git clone https://github.com/dgroddick/ansible_openldap_server.git openldap_server
```

Once the role has been downloaded, you'll need a playbook to run it. If you've already got a method of running Ansible roles then you should
continue using that, otherwise a playbook might look something like this:

```
---
- name: Setup OpenLDAP Server
  hosts: ldap
  gather_facts: yes
  become: yes

  tasks:
  - name: Run openLDAP role
    import_role:
      name: openldap_server
```

Running the Ansible playbook with the following command:

```
$ ansible-playbook -i hosts openldap.yml
```