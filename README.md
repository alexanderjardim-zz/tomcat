Tomcat
========

Tomcat ansible role.

1. All my roles make the assumption that host machines don't have internet connection, as this is the standard behavior of production machines in most companies. So, all the necessary dependencies will be downloaded to the control machine and after that pushed to the host machines. Keep in mind that you will need disk space for these downloads on your control machine.
1. I try to not use any package manager, at all. This way, you will not depend on more than one maintainer for the same software (the software original writer, and the package management team). Going this way, it is your choice to install using root or not. Which I always advise to don't use, if you can.
1. I try to keep all of my roles free from sudo or root access. If you want to use root, it is your choice and not an specific demand, and I will keep this way as long as I can.


Requirements
------------

none

Role Variables
--------------

- tomcat_dir: '/home/vagrant/tomcat'
- tomcat_major_version: '7'
- tomcat_minor_version: '0'
- tomcat_micro_version: '53'
- tomcat_version: "{{tomcat_major_version}}.{{tomcat_minor_version}}.{{tomcat_micro_version}}"
- tomcat_package: 'apache-tomcat-{{tomcat_version}}.tar.gz'
- tomcat_download_url: "http://ftp.unicamp.br/pub/apache/tomcat/tomcat-{{tomcat_major_version}}/v{{tomcat_version}}/bin/{{tomcat_package}}"
- tomcat_download_dir: '~/Downloads'
- tomcat_log_level: 'FINE'
- tomcat_log_dir: '${catalina.base}/logs'
- tomcat_log_limit: 1024
- tomcat_port: 8080
- tomcat_shutdown_port: 8005
- tomcat_ajp_port: 8009
- tomcat_redirect_port: 8443
- tomcat_connection_timeout: 20000
- tomcat_users: [
  { name: 'tomcat', password: 'tomcat', roles: 'tomcat,admin-gui'}
]

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
