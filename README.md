# qb.backup - Backup server setup role

This role is intended to setup a FreeBSD Jail running on a FreeNAS server.

This Jail is intended to run the Python script
[qb.backup](https://github.com/quarkslab/qb.backup).

You can see an example playbook implementing this role here:
[ansible-playbook-qb.backup](https://github.com/quarkslab/ansible-playbook-qb.backup).

## Requirements

Python 3.7 must be manually installed in the jail prior to this role execution:
```console
# pkg bootstrap
# pkg update -f
# pkg install python37
```

## Notes

`become` and `become_user` cannot be used in the role when using the
`sshjail` connector, as they would affect the "outer" connection (to FreeNAS)
instead of the command executed in the jail.
