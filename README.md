virtualbox-guest
================

This role installs the virtualbox guest additions.
It removes already installed version, if the desired version is different from the currently installed one.

Requirements
------------

This role requires Ansible 2.0 or higher.

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows.

```yaml
# this version determines the version of the guest additions that will be installed
virtualbox_version: 5.0.26
# the checksum of the iso fil
iso_checksum: "sha256:7458ee5a7121a7d243fd6a7528ba427945d9120c5efc7cd75b3951fb01f09c59"
# specifiy where the downloaded iso file will be placed
iso_download_path: "/opt"
# mount path where iso will mounted
iso_mount_path: /mnt/virtualbox
# easier path based on above variables
virtualbox_iso_path: "{{iso_download_path}}/VBoxGuestAdditions_{{virtualbox_version}}.iso"
```

Example Playbook
----------------

```yaml
- hosts: localhost
  remote_user: root
  roles:
    - ansible-role-virtualbox-guest
```

License
-------

BSD

Author Information
------------------

Richard Attermeyer

* [Blog](http://www.rattermyer.de)
* [Github](https://github.com/rattermeyer)
* [Twitter](https://twitter.com/rattermeyer)
