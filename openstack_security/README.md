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

Example Playbook
----------------

    - hosts: local
      name: Create kubernetes hosts
      gather_facts: false
      roles:
        - role: openstack_security

License
-------

BSD

Author Information
------------------

Andreas Kaminski
