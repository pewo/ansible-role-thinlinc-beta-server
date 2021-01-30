ansible-role-thinlinc-beta-server
=================================

This is a role that installs the latest Thinlinc beta release. 
Please read [README.md]https://github.com/cendio/ansible-role-thinlinc-server/blob/master/README.md

Requirements
------------

This role uses the role https://github.com/cendio/ansible-role-thinlinc-server/releases to install a Thinlinc server

Role Variables
--------------

thinlinc_beta_version: "4.12.1"
thinlinc_beta_build: "6724"
thinlinc_beta_server_bundle: "tl-4.12.1beta1-server.zip"
thinlinc_beta_download_dir: "/tmp"

Dependencies
------------

https://github.com/cendio/ansible-role-thinlinc-server/releases

Example Playbook
----------------

```yaml
- hosts: thinlinc_servers
  roles:
    - { role: ansible-role-thinlinc-beta-server, thinlinc_accept_eula: "yes" }
```

The final step is to apply the playbook to the inventory, like this:

`ansible-playbook -i inventory thinlinc.yml`

License
-------

BSD

Author Information
------------------

peter.wirdemo at gmail.
