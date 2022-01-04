EPrints ansible role
====================

This repository contains an ansible [role](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html) which installs [EPrints](https://www.eprints.org) on a Rocky Linux 8 based host.

Testing
-------
This repository has a sample playbook file and Vagrantfile to test the installation. Running the following:
```
vagrant up --provision
```
Should bring up a virtual machine with EPrints ready for you to create digital repositories.

TODO
----

The following tasks can be carried out once the VM is up, but it would be nice to put them in the role:

* Apache cannot start because the file `/usr/share/eprints/cfg/apache.conf` which is included in `/etc/httpd/conf.d/eprints.conf` looks for configuration files using `Include /usr/share/eprints/cfg/apache/*.conf`. This fails when no repositories are present - changing this line to `IncludeOptional /usr/share/eprints/cfg/apache/*.conf` enables Apache to start though.
* MariaDB service is not started - there is some stuff in `roles/eprints/tasks/mysql-secure.yml` I picked up from somewhere which does a similar thing to running the `mysql_secure_installation` command.