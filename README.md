ansible-role-thinlinc-beta-server
=================================

This is a role that installs the latest Thinlinc beta release. 
Please read:
  - [ansible-role-thinlinc-server/README.md](https://github.com/cendio/ansible-role-thinlinc-server/blob/master/README.md) 


Requirements
------------

This role uses the role [ansible-role-thinlinc-server](https://github.com/cendio/ansible-role-thinlinc-server) to install a beta Thinlinc server

Role Variables
--------------

```yaml
thinlinc_beta_accept_eula: "no"
```

By changing this to "yes", you agree to the terms specified in the
ThinLinc End User License Agreement. NOTE: Setting this to yes is a
requirement for installing and using ThinLinc.

```yaml
thinlinc_beta_version: "4.14.0"
thinlinc_beta_build: "2394"
thinlinc_beta_server_bundle: "/local/artifactory/tl-4.14.0beta1-server.zip"
```

ThinLinc version, build number and bundle names.


Dependencies
------------

[ansible-role-thinlinc-server](https://github.com/cendio/ansible-role-thinlinc-server)

Examples
--------

The role uses three groups - thinlinc_masters, thinlinc_agents and
thinlinc-servers. Here's an example inventory file with one master
server and three agent servers:

```yaml
[thinlinc_masters]
tl-master-01.example.com

[thinlinc_agents]
tl-agent-01.example.com
tl-agent-02.example.com
tl-agent-03.example.com

[thinlinc_servers:children]
thinlinc_masters
thinlinc_agents
```

Now that we got both a role and an inventory, connect the dots by
applying the thinlinc-server role to the thinlinc_servers group with a
`thinlinc.yml` playbook:

```yaml
- hosts: thinlinc_servers
  roles:
    - { role: ansible-role-thinlinc-beta-server, thinlinc_beta_accept_eula: "yes" }
```

The final step is to apply the playbook to the inventory, like this:

`ansible-playbook -i inventory thinlinc.yml`

License
-------

GPLv3.

Author Information
------------------

peter.wirdemo at gmail.
