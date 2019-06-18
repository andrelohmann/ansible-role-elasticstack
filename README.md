elasticstack
============

[![Build Status](https://travis-ci.org/andrelohmann/ansible-role-elasticstack.svg?branch=master)](https://travis-ci.org/andrelohmann/ansible-role-elasticstack)

Simple role to install a single node (unsecured) ElasticStack with kibana and beats templates. Development is still in an early stage and usage in production is not suggested!

!!! Make Kibana listen only on local host and put a BasicAuth secured Proxy in front of it !!!

!!! Make elasticsearch listen on all devices (0.0.0.0) and restrict access using iptables !!!

Role Variables
--------------

    elasticsearch_heap_size: 1g
    elasticsearch_install_elasticsearch: True
    elasticsearch_install_kibana: True
    # elasticsearch_network_host: "localhost" # elasticsearch listens here
    # elasticsearch_listen_ip: "localhost" # ip address to which kibana and beats should connect to
    # elasticsearch_kibana_listen_ip: "localhost" # kibana listens here
    elasticsearch_release: 7.1.1

    elasticsearch_install_auditbeat: True
    elasticsearch_install_filebeat: True
    elasticsearch_install_heartbeat: True
    elasticsearch_install_metricbeat: True
    elasticsearch_install_packetbeat: True

Example Playbook
----------------

    - hosts: elasticsearch
      roles:
         - { role: andrelohmann.elasticsearch }

Todo
----

Implement the following instructions into the role

https://blog.netways.de/2017/09/14/secure-elasticsearch-and-kibana-with-an-nginx-http-proxy/

or

implement SearchGuard

License
-------

MIT

Author Information
------------------

https://github.com/andrelohmann
