Role Name
=========

A utility playbook to generate custom certificates using an existing role. This is to support testing where custom signed certificates are needed.


Requirements
------------


Plays and Role Variables
------------------------

- ansible_name_module: The name of the module this role is part of. This is used to track context when this role is run in a playbook as part of other plays.  
- certs_dir: The name of the directory to place the generated certificate files into.
- generate_ca: Denotes whether to generate the CA or not. If not it is expected that existing CA files are provided to use for signing the generated certificates.
- ca_key_file: Path to the existing or to be generated key file for the custom CA
- ca_csr_file: Path to the to be generated CSR file for the custom CA. This is only when the custom CA is being generated.
- ca_cert_file: Path to the existing or to be generated pem certificate file for the custom CA
- ca_cert_cm: The common name to be used for the to be generated custom CA. This is only when the custom CA is being generated.
- app_certs: The list structure containing information about the custom signed certificates being generated. 
   - cert_cm: The common name to be used for the to be generated current custom certificate.
   - csr_file: Path to the to be generated CSR file for the current custom certificate.
   - cert_file: Path to the to be generated pem certificate file for the current custom certificate.

Dependencies
------------
This role uses the https://github.com/cadjai/generate-self-signed-certificates-and-ca.git role to provision custom signed certificates.


Installation and Usage
-----------------------
Clone the repository to where you want to run this from .
Ensure you install all requirements using `ansible-galaxy install -r requirements.yml --force -p roles` before performing the next steps.
Finally before running the playbook make sure to set and update the variables as appropriate to your use case.

Playbooks
---------
To run the main playbook use the ansible-playbook command as follows
`ansible-plabook create-self-signed-certs.yml`


License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
