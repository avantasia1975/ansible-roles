vault_helm
====================

Installs vault helm chart and etcd as backend

Requirements
------------

Helm needs to be installed.
Kubernetes.core must be installed
```
 ansible-galaxy collection install kubernetes.core
```

Role Variables
--------------

- vault_helm__namespace  
  Namespace to deploy the stack to. Default: test  

- vault_helm_kubeconfig  
  Kubernetes config to use. Default: ~/.kube/conf


Example Playbook
----------------

    - hosts: local
      gather_facts: false
      roles:
        - role: vault_helm_stack
          vars:
            vault_helm_namespace: test

License
-------

BSD

Author Information
------------------

Andreas Kaminski
---
