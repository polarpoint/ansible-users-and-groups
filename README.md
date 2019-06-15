ansible-users-groups-role	 
 =========

 Ansible common role to maintain users and groups

 Requirements
 ------------

 Centos/Redhat/Fedora
 Debian/Ubuntu


 Role Variables
 --------------

limit to the role you are interested in i.e.

```
ansible-playbook -i inventory/production site.yml --limit jenkins-master
```

or in your Vagrantfile as...

```
ansible.limit = "jenkins-master"
```

Define users and groups in the group_vars like below in the server file.
 
 
 ```
├── group_vars
│   ├── all
│   └── jenkins-master
│       └── server.yml
└── inventory
 
 as follows 
 
---
user_groups:
 - { group_name: "jenkins", system_group: true}
users:
  - { user_name: "jenkins", primary_group: "jenkins", append_groups: true, groups: "", system_user: true, generate_user_ssh_key: true, ssh_key_file: ".ssh/id_rsa"}

 ```
 


 License
 -------

 BSD

 Author Information
 ------------------

 Surjit Bains <surj@polarpoint.io> 
