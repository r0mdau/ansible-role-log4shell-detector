Ansible Role: log4shell-detector
================================

Role to run [log4shell-detector](https://github.com/Neo23x0/log4shell-detector) script on Debian and Rhel OS.

Features :
* install python3, git
* clone Neo23x0/log4shell-detector repository
* launch log4shell-detector.py script
* copy log4shell-detector output on local files in json

Many thanks to [Neo23x0](https://github.com/Neo23x0) for the log4shell detector python script.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    log4shell_args: "-p /var/log"

List of arguments here [Neo23x0/log4shell-detector](https://github.com/Neo23x0/log4shell-detector/blob/main/README.md)

Dependencies
------------

None.

Example Playbook
----------------

Playbook example : r0mdau/ansible-log4shell-detector

    - hosts: javaservers
      vars_files:
        - vars/main.yml
      roles:
        - { role: r0mdau.log4shell-detector }

*Inside playbook `vars/main.yml`*:

    log4shell_args: "-p /var/log"

Scripts
-------
///TODO
```
ansible-playbook tests/test.yml -i tests/inventory --syntax-check
```

License
-------

Apache-2.0

Author Information
------------------

r0mdau[¹](https://github.com/r0mdau)
