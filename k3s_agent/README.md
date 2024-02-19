k3s_agent
=========

Install k3s in agent mode on servers

Role Variables
--------------

- k3s_version  
  Version of k3s

- k3s_server_token  
  Token to connect to the k3s-server

- k3s_server_url
  The k3s server url to connect to.

Example Playbook
----------------

    - hosts: agent
      roles:
         - k3s_agent
           vars:
             - k3s_server_token: "my-token"
             - k3s_server_url: "my-url"

License
-------

BSD

Author Information
------------------

Andreas Kaminski
