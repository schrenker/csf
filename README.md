CSF
=========

Ansible role used to install ConfigServer Firewall.

Role Variables
--------------

Soon to be added, covers most of CSF options + installation options.


Example Playbook
----------------

For base installation with default values, there is no need to define any variables. However, if you want to change any of the CSF settings, do it directly in role variables.

    - hosts: servers
        roles:
            - role: csf
            csf_tcp_out: "22, 25, 80, 443"
            csf_tcp_in: "22, 80"
            csf_docker: "1"
License
-------

BSD

Author Information
------------------

Sebastian Zawadzki
zawadzkis95@gmail.com
https://github.com/schrenker

