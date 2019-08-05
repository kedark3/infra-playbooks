Role Name
=========

This is a role written for deploying VMware VM Deployments.

Requirements
------------

You might need to have pyVmomi installed on your system as this role attempts to run against localhost. Uses `connection: local`

Role Variables
--------------
Role variables are self-explanatory and provided in vmware_vm_provisioning_vars.yml.sample for you to checkout.
For this role to run you need to have variables file `vars/vmware_vm_provisioning_vars.yml` or supply all variables as extra vars
during execution.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - name: Create VM on VMware
      hosts: localhost
      connection: local
      roles:
        - vmware_deploy_vms`

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
