Ansible Role: smtpdebuggingserver
=================================

Configures a fake smtp server as a systemd service.

Uses python's class smtpd.DebuggingServer: https://docs.python.org/3/library/smtpd.html#debuggingserver-objects

Requirements
------------

python3
systemd

Role Variables
--------------

Configure the local host to bind the server:

```
smtp_debugging_server_host: localhost
```

Configure the local port to bind the server:

```
smtp_debugging_server_port: 8025
```

Configure a user to run systemd service:

```
smtp_debugging_server_systemd_user: root
```

Configure the systemd service type:

```
smtp_debugging_server_systemd_type: simple
```

Dependencies
------------

No dependencies.


Example Playbook
----------------

Example with default variables:

    - hosts: servers
      roles:
         - { role: rsicart.smtpdebuggingserver }


Example configuring the server to listen on default ipv4 address:

    - hosts: servers
      roles:
        - role: rsicart.smtpdebuggingserver
      vars:
        smtp_debugging_server_host: "{{ ansible_default_ipv4.address | default(ansible_all_ipv4_addresses[0], true) }}"


License
-------

GPL-3.0-only

Author Information
------------------

https://gitlab.com/rsicart
https://github.com/rsicart
