Supervisor
==========

This Ansible role installs [Supervisor](http://supervisord.org/) using [pip](http://pip.readthedocs.org/en/latest/) and provides a mechanism for managing application processes. It has only been tested using Ansible 1.6 on CentOS 6.5 but should work on other EL 6 distributions.

Role Variables
--------------

All variables have [defined defaults](https://github.com/avtar/ansible-supervisor/blob/master/defaults/main.yml) and do not need to be modified on supported operating systems with the exception of the following:


 * ```supervisor_app_name``` - The application's name which is used to name the process' configuration file.

 * ```supervisor_app_command``` - The command and its arguments that need to be executed in order to start the application's process.

 * ```supervisor_app_directory``` - The full path of the application's directory.

 * ```supervisor_app_user``` - The user account that will own the process and log files.
 
The role will fail if the above four variables are not defined.

Usage
-----

Example playbook:

```
- hosts: servers
  roles:
    - role: supervisor
      supervisor_app_name: 'awesome_nodejs_app'
      supervisor_app_command: 'node bin/script.js'
      supervisor_app_directory: '/srv/awesome_nodejs_app'
      supervisor_app_user: 'nobody'
      supervisor_app_env_vars:
        node_env: production
```

License
-------

Apache 2.0

Author Information
------------------

Avtar Gill

Copyright 2014 OCAD University
