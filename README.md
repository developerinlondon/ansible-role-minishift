ansible-role-minishift
===========================

`ansible-role-minishift` installs [Minishift](https://github.com/minishift/minishift) and sets up prerequisites of it.
The supported OS distributions are as follows:

* Mac OSX Sierra
* Fedora 25

For Fedora, a virtual network named `default` must be running before starting minishift and the network name must be exactly `default`. `minishift start` fails as it cannot find such a network unless it exists. `minishift start` does not create the network either even if it does not exist.
`tasks/Fedora.yml` creates a virtual network named default.

Requirements
------------

* Ansible 2.3 or later


Role Variables
--------------

* `minishift_path_prefix` specifies PATH to install docker-machine, docker-machine-driver-kvm and minishift.
* `minishift_brew_prefix` specifies PATH to install minisfhift using brew.


Example Playbook
----------------

```
- hosts: 127.0.0.1
  connection: local
  roles:
    - { role: ansible-role-minishift }
```

License
-------

BSD

Author Information
------------------

Naoya Hashimoto <nhashimo@redhat.com>
