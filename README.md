ansible-role-thinlinc-beta-server
=================================

This is a role that installs the latest Thinlinc beta release. 
Please read:
  - [ansible-role-thinlinc-server README.md](https://github.com/cendio/ansible-role-thinlinc-server/blob/master/README.md) 


Requirements
------------

This role uses the role https://github.com/cendio/ansible-role-thinlinc-server/releases to install a Thinlinc server

Role Variables
--------------

```yaml
thinlinc_accept_eula: "no"
```

By changing this to "yes", you agree to the terms specified in the
ThinLinc End User License Agreement. NOTE: Setting this to yes is a
requirement for installing and using ThinLinc.

```yaml
thinlinc_beta_version: "4.12.1"
thinlinc_beta_build: "6724"
thinlinc_beta_server_bundle: "tl-4.12.1beta1-server.zip"
thinlinc_beta_download_dir: "/tmp"
```

ThinLinc version, build number, bundle names and download directory.


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

GPLv3.

Author Information
------------------

peter.wirdemo at gmail.
