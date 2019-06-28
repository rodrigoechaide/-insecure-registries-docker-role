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

Variables explanation:

* `url` Docker registry URL
* `login` Boolean variable which specify if a docker login is needed or not to the specified registry
* `user` If `login` is true, specify registry user to login with. A good way to specify this value would be with Ansible Vault. If `login` is false there is no need to specify this variable.
* `pass` If `login` is true, specify registry pass to login with. A good way to specify this value would be with Ansible Vault. If `login` is false there is no need to specify this variable.
* `cert` Boolean variable which indicates if the specified registry uses https along with a self-signed certificate or if it just only uses http
* `cert_file_url` If `cert` is true, specify `cert_file_url` in order to download the self-signed certificate into `docker_certs_path`


Variables can be modified as needed. `insecure_docker_registries` dictionary can contain as many registries as needed and a good practice is to name each registry as registry_01, registry_02 and so on but any name could be configured.

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
