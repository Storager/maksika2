Role Name
=========

Role installs docker engine to Ubuntu host

![Image of Yaktocat](https://travis-ci.org/Storager/role.docker.svg?branch=master)

Role Variables
--------------

Absent in current release.

Dependencies
------------

Can be used in Ubuntu 16.04 only.

Structure
---------

tasks
- main.yml - main playbook
- redmine.yml - specific for service playbook



Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: role.docker }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
