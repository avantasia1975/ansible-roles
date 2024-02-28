K8s_monitoring_stack
====================

Installs a monitoring stack to a kubernetes cluster  
this includes  
* Prometheus ( Prometheus operator )
* Mimir
* Loki
* Grafana
* Promtail

Requirements
------------

Helm needs to be installed.
Kubernetes.core must be installed
```
 ansible-galaxy collection install kubernetes.core
```

Role Variables
--------------

- k8s_monitoring_stack_namespace  
  Namespace to deploy the stack to. Default: test  

- k8s_monitoring_stack_kubeconfig  
  Kubernetes config to use. Default: ~/.kube/conf

- k8s_monitoring_grafana_user  
  Grafana user to use. Default: test

- k8s_monitoring_grafana_password  
  Grafana password. Default: test

- k8s_monitoring_grafana_replicas  
  Grafana replicas to deploy. Default: 1

- k8s_monitoring_minio_user  
  Minio user. Default: k8s_monitoring-user

- k8s_monitoring_minio_password  
  Minio user password. Default: 8s_monitoring_password
  
- k8s_monitoring_loki_basic_auth_user  
  Loki user. Default: loki

- k8s_monitoring_loki_basic_auth_password  
  Loki user password. Default: loki

- k8s_monitoring_loki_tenant  
  Tenant to use. Defalut: self-monitoring

- k8s_monitoring_mimir_basic_auth_user  
  Mimir user. Default: mimir

- k8s_monitoring_mimir_basic_auth_password  
  Mimir password. Default: mimir

- k8s_monitoring_mimir_tenant  
  Mimir tenent to use. Default: anonymous


Example Playbook
----------------

    - hosts: local
      gather_facts: false
      roles:
        - role: k8s_monitoring_stack
          vars:
            k8s_monitoring_stack_namespace: test

License
-------

BSD

Author Information
------------------

Andreas Kaminski
---
