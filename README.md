Ansible Role: log4shell-detector
================================

Role to run [log4shell-detector](https://github.com/Neo23x0/log4shell-detector) script on Debian and RHEL base OS.

Features :
* install python3, git
* clone Neo23x0/log4shell-detector repository
* launch log4shell-detector.py script
* copy log4shell-detector output on local files in json
* possible to pass a second scan

Many thanks to :
* [Neo23x0](https://github.com/Neo23x0) for the log4shell detector python script.
* [hillu](https://github.com/hillu) for the simple local log4j vulnerability scanner written in Go.

Quick start
-----------

If you are not familiar with ansible and need the simpliest documentation to run the detection to multiple servers, go directly 
 to the [playbook example documentation](https://github.com/r0mdau/ansible-log4shell-detector).

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    log4shell_args: "-p /var/log --quick"
    second_scan_args: "/"
    second_scan: false

List of arguments for:
* `log4shell_args`   --> [Neo23x0/log4shell-detector](https://github.com/Neo23x0/log4shell-detector/blob/main/README.md)
* `second_scan_args` --> [hillu/local-log4j-vuln-scanner](https://github.com/hillu/local-log4j-vuln-scanner)

Dependencies
------------

None.

Example Playbook
----------------

Playbook example : [r0mdau/ansible-log4shell-detector](https://github.com/r0mdau/ansible-log4shell-detector)

    - hosts: javaservers
      vars_files:
        - vars/main.yml
      roles:
        - { role: r0mdau.log4shell-detector }

*Inside playbook `vars/main.yml`*:

    log4shell_args: "-p /var/log"
    second_scan_args: "/"
    second_scan: true

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
