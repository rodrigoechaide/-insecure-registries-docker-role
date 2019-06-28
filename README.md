Insecure Registries Docker Role
===============================

Role to configure insecure registries into docker.

Note: Using insecure registries is not a good practice but they can be very useful in a development or testing enviroment.

Requirements
------------

Only docker installed is required.

Role Variables
--------------

Available variables are listed below, along with default values (see defaults/main.yml):

```
insecure_docker_registries:
  registry_01:
    url: ''
    login: false
    user: ''
    pass: ''
    cert: false
    cert_file_url: ''

docker_certs_path: '/etc/docker/certs.d'

```

Variables can be modified as needed. Also insecure_docker_registries dictionary can contain as many registries as needed and a good practice is to name each registry as registry_01, registry_02 and so on but any name can be configured.

Dependencies
------------

Role Dependencies:

    geerlingguy.docker

Example Playbook
----------------

```
    - hosts: all
      roles:
         - role: insecure-registries-docker-role
```
License
-------

MIT

Author Information
------------------

Echaide Rodrigo.
