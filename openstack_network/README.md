openstack_network
=================

Create openstack network components

Requirements
------------

openstack ansible collection

Role Variables
--------------

- openstack_network_name  
  Name of the network to create. Default "my-network"
  
- openstack_network_subnet  
  Name of the subnet. Default "my-subnet"

- openstack_network_cidr  
  Cidr to use. Default "192.168.102.0/24"

- openstack_network_gateway_ip  
  Gateway ip address. Default "192.168.102.1"

- openstack_network_dns_nameservers  
  List of nameserver to use. Default []
  
- openstack_network_router_name  
  Name of the router. Default "my-router"

- openstack_network_enable_snat  
  Enable snat. Default "true"

- openstack_network_external_network  
  Name of the external net. Default "ext-net"


Example Playbook
----------------

    - hosts: local
      name: Create kubernetes hosts
      gather_facts: false
      roles:
        - role: openstack_network
          vars:
            openstack_network_dns_nameservers: 
              - "8.8.8.8"

License
-------

BSD

Author Information
------------------

Andreas Kaminski
