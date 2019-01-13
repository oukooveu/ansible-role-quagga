Ansible role: Quagga
=========

Install Quagga routing server for RedHat/CentOS.

Requirements
------------

None.

Role Variables
--------------

```
quagga_conf:
  bgpd:
    enabled: true
    config: |
      router bgp 65001
        bgp router-id {{ ansible_default_ipv4.address }}
        network 192.168.1.0/24
        neighbor 169.254.1.2 remote-as 65002
      !
      line vty
      !
```

Dependencies
------------

None.

Example Playbook
----------------

```
- hosts: servers
  roles:
    - quagga
```

License
-------

Apache 2.0

Author Information
------------------

Daniil Kupchenko, kupchenko@gmail.com
