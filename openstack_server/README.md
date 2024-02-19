openstack_server
================

Install openstack server 

Requirements
------------

ansible openstack collection

Role Variables
--------------

- openstack_server_ssh_key_name  
  Name of the ssh-key. Default "my-ssh-key"

- openstack_server_public_key  
  Ssh key. Default ""

- openstack_server_name  
  Name of the server. Default "my-server"

- openstack_server_flavor  
  Flavor to use. Default m1.small

- openstack_server_public_key_file  
  Keyfile of ssh-key. Default ""

- openstack_network_name  
  Network name. Default "my-network"

- openstack_server_image
  Regex of image to install. Default "Ubuntu Focal"

- openstack_server_auto_ip  
  Use external ip address. Default "true"

- openstack_server_security_groups  
  List of security groups to use. Default [default]
  
- openstack_server_userdata  
  Cloud-init-script to use. Default ""
  
- openstack_server_count  
  Number of instances to install. Default 3 

- openstack_server_ansible_group  
  Ansible group to assign the host to. Default "all"

Example Playbook
----------------

    - hosts: local
      gather_facts: false
      roles:
        - role: openstack_server
          vars:
            openstack_server_name: "kube-server"
            openstack_server_ansible_group: "server"
            openstack_server_count: 1
            openstack_server_security_groups:
              - default
              - my-security-group
        - role: openstack_server
          vars:
            openstack_server_name: "kube-agent"
            openstack_server_ansible_group: "agent"
            openstack_server_count: 2
            openstack_server_security_groups:
              - default
              - my-security-group

License
-------

BSD

Author Information
------------------

Andreas Kaminski
