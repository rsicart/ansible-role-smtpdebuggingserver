Role Name
=========

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

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

GPL-3.0-only

Author Information
------------------

https://gitlab.com/rsicart
