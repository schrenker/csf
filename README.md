CSF
=========

[![CSF](https://github.com/schrenker/csf/actions/workflows/ansible_lint.yml/badge.svg)](https://github.com/schrenker/csf/actions/workflows/ansible_lint.yml)

Ansible role used to install ConfigServer Firewall.  

This role was tested on following systems:  

- centOS 7
- centOS 8
- AlmaLinux 8
- Rocky Linux 8
- Debian 9
- Debian 10
- Ubuntu 18.04
- Ubuntu 20.04
- Ubuntu 20.10
- Ubuntu 21.04

Role Variables
--------------

Most of the variables cover configuration options of CSF from /etc/csf/csf.conf file. These variables take default CSF values, and are defined as csf_<csf.conf_option_name> in lowercase.  

### Notable variables:  

csf_checksum - sha256 checksum of downloaded tgz file  
csf_tgz - path to downloaded tgz file  
csf_unpack - directory where tgz archive is unpacked  

csf_conf_template - By default "csf.conf.truncated.j2" - Default CSF config file provides verbose descriptions to every available option. This role sends file without these descriptions, resulting in smaller file. To revert this, change variable value to "csf.conf.j2"  

csf_testing - By default in CSF, this takes value of 1. This role sets this value to 0 immediately in order to launch LFD daemon. Override this variable to disable LFD daemon.  


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

