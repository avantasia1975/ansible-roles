generate_ca
===========

Generates a certificate from a given or created root ca

Role Variables
--------------

- generate_ca_generate_rootca_key  
  if true, a root-ca root key will be created. Default is true

- generate_ca_generate_rootca_crt   
  if true, a root-ca root crt will be created. Default is true

- generate_ca_passphrase  
  The passphrase used for the root-ca key. Default "my-passphrase"

- generate_ca_root_key_file  
  File contains the root-ca key. Default "root_ca.key"

- generate_ca_root_crt_file  
  File contains the root-ca cert. Default "root_ca.crt"

- generate_ca_root_key   
  The root-ca key. Provided as var or read from file. Default ""

- generate_ca_root_crt  
  The root-ca cert. Provided as var or read from file. Default ""

- generate_ca_cert_dir  
  Local directory where to store the certs. Default "cert"

- generate_ca_country_name  
  Country for the csr. Default "de"

- generate_ca_org_name  
  Company for the csr. Default "example"

- generate_ca_common_name  
  Common name for the csr. Default "{{ inventory_hostname }}"

- generate_ca_subject_alt_name  
  Alternative names for the cert. Default ["DNS:{{ ansible_host }}"]

- generate_ca_certificate_file  
  Filename for the certificate. Default "{{ generate_ca_common_name }}-certificate.crt"

- generate_ca_privatekey_file  
  Filename for the private.key. Default "{{ generate_ca_common_name }}-private.key"

- generate_ca_run_once  
  If false, a certificate will be created for each host. Default false
  It's a good idea to adjust common and san names accordingly

- generate_ca_copy_cert  
  If true, copies files to the host. Default false

- generate_ca_copy_cert_folder  
  Remote folder where to store the certificates. Default "/var/cert"

Example Playbook
----------------


    - hosts: servers
      roles:
        - generate_ca
          vars:
            generate_ca_common_name: "www.example.com"
            generate_ca_subject_alt_name:
              - "DNS:examle.com"

   

License
-------

BSD

Author Information
------------------

Andreas Kaminski
