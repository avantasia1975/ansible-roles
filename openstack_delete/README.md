openstack_delete
================

Delete openstack resources

Requirements
------------

openstack ansible collection


Role Variables
--------------

- openstack_server_names  
  List of servernames to delete. Default ["my-server"]

- openstack_server_ssh_key_name
  Name of the ssh key to delete. Default "my-ssh-key"

- openstack_network_name  
  Name of the network to delete. Default "my-network"

- openstack_network_subnet  
  Name of the subnet to delete. Default "my-subnet"

- openstack_network_router_name  
  Name of the router to delete. Default "my-router"

- openstack_security_group_name  
  Name of the security group to delete. Default "my-security-group"

Example Playbook
----------------

    - hosts: all
      roles:
        - role: openstack_delete
          vars:
            openstack_server_names:
              - "kube-server"
              - "kube-agent"

License
-------

BSD

Author Information
------------------

Andreas Kaminski
