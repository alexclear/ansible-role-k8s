K8S
=========
This role installs Kubernetes cluster v1.10

Description
------------

Kubernetes 1.10 + Calico

Role Variables
--------------

kubernetes:
  user: kuber
  master_ip: 10.73.64.132
  token: pm7m13.mkxgm9tvelm0x4pb
  pod_network_cidr: 192.168.0.0/16
  admin_conf: /etc/kubernetes/admin.conf

Example
----------------

    - hosts: k8s-cluster
      become: yes
      become_user: root
      roles:
        - role: docker
        - role: k8s/common

    - hosts: k8s-master
      become: yes
      become_user: root
      roles:
        - role: k8s/master

    - hosts: k8s-slaves
      become: yes
      become_user: root
      roles:
        - k8s/slave


License
-------

GPLv3+

Author Information
------------------

This role was written by Dmitrii Kashin aka freehck
