Tomcat
========

Tomcat ansible role.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

- tomcat_dir: '/home/vagrant/tomcat'
- tomcat_major_version: '7
- tomcat_minor_version: '0
- tomcat_micro_version: '53
- tomcat_version: "{{tomcat_major_version}}.{{tomcat_minor_version}}.{{tomcat_micro_version}}
- tomcat_package: 'apache-tomcat-{{tomcat_version}}.tar.gz
- tomcat_download_url: "http://ftp.unicamp.br/pub/apache/tomcat/tomcat-{{tomcat_major_version}}/v{{tomcat_version}}/bin/{{tomcat_package}}
- tomcat_dist: 'apache-tomcat-7.0.53
- tomcat_log_level: 'FINE
- tomcat_log_dir: '${catalina.base}/logs
- tomcat_log_limit: 102
- tomcat_port: 808
- tomcat_shutdown_port: 800
- tomcat_ajp_port: 800
- tomcat_redirect_port: 844
- tomcat_users: [  { name: 'tomcat', password: 'tomcat', roles: 'tomcat,admin-gui'}]

Dependencies
------------

alexanderjardim.oracle_jdk

Example Playbook
-------------------------

```
    - hosts: servers
      roles:
         - { role: alexanderjardim.tomcat }
```

License
-------

BSD

Author Information
------------------

alexander.ramos.jardim+tomcat@gmail.com