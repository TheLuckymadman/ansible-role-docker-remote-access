Role Name
=========

The role is used for setting the remote access up for the docker daemon.

Requirements
------------

1. Need docker daemon installed with no custom systemd daemon settings because they will be overridden. 
   If you have custom systemd daemon settings, I should add them to ./file/docker.service file. 
2. You should prepare certificates to set up remote access by using this role. 
   You can use the official docs to prepare the certificates: https://docs.docker.com/engine/security/protect-access/

Role Variables
--------------

There are some vars with the default values in defaults/main.yml:
ca_crt_path: "files/ca.crt" - path to CA cert
server_cert_path: "files/server.crt" - path to server cert
server_key_path: "files/server.key" -  path to server cert's key
cert_dest_dir: "/etc/docker/pki" - the place on a server where the certificates will be store.

Dependencies
------------

No dependencies.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
         - ansible-role-docker-remote-access

License
-------

BSD

Author Information
------------------

Kirill klepeshkin@gmail.com
