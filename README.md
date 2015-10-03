# Ansible Role: PPTP

[![Build Status](https://travis-ci.org/sparanoid/ansible-pptp.svg)](https://travis-ci.org/sparanoid/ansible-pptp)

Install PPTP VPN via Ansible.

## Features

- Install or upgrade `ppp` and `pptp` easily
- Tuning `sysctl`
- Update iptables rules
- Add / update PPTP users and passwords in YAML configs

## Requirements

This role requires Ansible 1.6 or higher and platform requirements are listed in the metadata file.

## Dependencies

None

## Example Playbooks

Install PPTP with default passwords:

In `pptp-vpn.yml`:

```yaml
- hosts: servers
  roles:
    - role: sparanoid.pptp
```

Overriding users and passwords:

```shell
$ ansible-playbook pptp-vpn.yml --extra-vars "@vpn-users.yml"
```

In `vpn-users.yml`:

```yaml
---
pptp_users:
  - { "user": "user1", "passwd": "pass1" }
  - { "user": "user2", "passwd": "pass2" }
```

Note: You can use `--tags users` to only execute user update tasks.

## License

GPLv3

## Author Information

**Tunghsiao Liu**

- Twitter: @[tunghsiao](http://twitter.com/tunghsiao)
- GitHub: @[sparanoid](http://github.com/sparanoid)
