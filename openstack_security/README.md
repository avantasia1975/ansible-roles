openstack_security
==================

Install openstack security group

Requirements
------------

ansible openstack collection

Role Variables
--------------

- openstack_security_group_name
  Name of the security group. Default "my-security-group"

- openstack_security_group_tcp_ports
  List of tcp ports to open. Default 22

Example Playbook
----------------

    - hosts: local
      name: Create kubernetes hosts
      gather_facts: false
      roles:
        - role: openstack_security
          vars:
            openstack_security_group_tcp_ports: [22, 6443, 80]

License
-------

BSD

Author Information
------------------

Andreas Kaminski
