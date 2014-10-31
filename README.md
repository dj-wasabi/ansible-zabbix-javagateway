dj-wasabi.zabbix-proxy
=========

This is an role for installing and maintaining the zabbix-javagateway. There are other roles for the server, javagateway and the agent. (Which will be available soon..)

* zabbix-server (https://galaxy.ansible.com/list#/roles/2070)
* zabbix-proxy (https://galaxy.ansible.com/list#/roles/2073)
* zabbix-javagateway ()

Requirements
------------

This role will work on:
* Red Hat
* Debian
* Ubuntu

So, you'll need one of those operating systems.. :-)

Role Variables
--------------

There are some variables in de default/main.yml which can (Or needs to) be changed/overriden:
* `zabbix_version`: This is the version of zabbix. Default it is 2.4, but can be overriden to 2.2 or 2.0.

Dependencies
------------

The java gateway can be installed on either the zabbix-server or the zabbix-proxy machine. So one of these should be installed. You'll need to provide an parameter in your playbook for using the javagateway.

When using the zabbix-server:
```
  roles:
     - { role: dj-wasabi.zabbix-server, server_javagateway: 192.168.1.2}
```
or when using the zabbix-proxy:
```
  roles:
     - { role: dj-wasabi.zabbix-proxy, zabbix_server_host: 192.168.1.1, proxy_javagateway: 192.168.1.2}
```

The above is assumed you'll using the 'dj-wasabi' zabbix roles. Don't know how to do this with other zabbix-server (or zabbix-proxy) roles from other members.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: zabbix-server
      sudo: yes
      roles:
         - { role: dj-wasabi.zabbix-server, server_javagateway: 192.168.1.2}
         - { role: dj-wasabi.zabbix-javagateway }

License
-------

GPLv3

Author Information
------------------

This is my first attempt to create an ansible role, so please send suggestion or pull requests to make this role better. 

Github: https://github.com/dj-wasabi/ansible-zabbix-proxy

mail: ikben [ at ] werner-dijkerman . nl
