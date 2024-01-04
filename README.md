hosts_file
==========

Configure localhost (ipv4 and ipv6) entries in `/etc/hosts` to: `ansible_hostname`.`hosts_file_local_domain`	`ansible_hostname`

Remove lines containing `raspberrypi`.

Notes
-----

The reasoning for using `127.0.1.1` and not `ansible_default_ipv4.address` is, that if a host is changing between lan/wifi or has a dynamic ip, hardcoding the ip would be bad.

Role Variables
--------------

| Name          | Comment                              | Default value |
|---------------|--------------------------------------|---------------|
| hosts_file_local_domain  | Local domain for localhost entries i.e. `example.lan`  | `local`          |

Example Playbook
----------------
```yaml
- name: Fix hosts file for Raspberry Pi
  hosts: rpis
  collections:
    - oxivanisher.linux_base
  roles:
    - role: oxivanisher.linux_base.hosts_file
```

License
-------

BSD

Author Information
------------------

This role is part of the [oxivanisher.linux_base](https://galaxy.ansible.com/ui/repo/published/oxivanisher/linux_base/) collection, and the source for that is located on [github](https://github.com/oxivanisher/collection-linux_base).
