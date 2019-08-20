Deploy Shinken Server
=========

This is an Ansible Role to Deploy Shinken Monitoring Server with Basic installation. This includes installation of various RPM and PIP packages that are required for Shinken to work. Also some of the default packs that are being pulled from GitHub are specific to VMware,Red Hat Virtualization(oVirt) and OpenStack. This is a good starting point for someone wanting to monitor their on premise infrastructure.

Post installation of shinken with this Ansible Role, you can explore Shinken further at https://shinken.readthedocs.io/


Requirements
------------

CentOS 7 server is tested for this Ansible Role. It may work with Fedora or RHEL 7 given that correct repos are added on it.

Role Variables
--------------

`epel_repo_url: <URL to EPEL Repo .rpm for your OS>`

`shinken_packs` variable will hold list of packs to be installed as given below.

```
shinken_packs:
  - pack1
  - pack2
  .
  .
  .
  - packN
```

`shinken_packs_from_git_repo`: If you want to install any packs that are not on shinken.io, but are in Git repo that you can clone, following variable may be used.
```
shinken_packs_from_git_repo:
  - repo_name: repo1
    repo_url: https://github.com/user/repo1
  - repo_name: repo2
    repo_url: https://github.com/user/repo2
  and so on.
```

`enforce_ipv4_check_host_alive:`  This variable dictates if you want to enforce IPv4 ping or ping6 for IPv6, as when Shinken installs, it adds itself as a host and tries to perform `check_host_alive` check which will then be used to perform ping checks against itself. If you don't have IPv6 configured correctly, please use IPv4 by setting following variable to true.
`enforce_ipv4_check_host_alive:  true`


Example Playbook
----------------

    - name: Deploy Shinken on vms created by previous play
      hosts: vmware_vms
      roles:
        - deploy_shinken_server

