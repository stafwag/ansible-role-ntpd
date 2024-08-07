# Ansible Role: ntpd

An ansible role to configure ntpd

## Requirements

### Supported platforms

* Archlinux
* Debian
* FreeBSD
* NetBSD
* OpenBSD
* RedHat
* Suse

## Role Variables
### OS related variables

The following variables are set by the role.

* **ntp_service**: the ntpd service for the operating system.
* **ntp_driftfile**: path of the ntp_driftfile for the operating system.

### Playbook related variables

* **ntp_conf**: Path to the ntp.conf. Defaults to /etc/ntp.conf.
* **ntp_servers**: list of the ntp_servers.
  Defaults to:
```
      - 0.be.pool.ntp.org
      - 1.be.pool.ntp.org
      - 2.be.pool.ntp.org
      - 3.be.pool.ntp.org
```

## Dependencies

None

## Example Playbooks

```
- name: configure ntp on the systems
  hosts: all
  become: true
  vars:
    ntp_servers:
      - 0.europe.pool.ntp.org
      - 1.europe.pool.ntp.org
      - 2.europe.pool.ntp.org
      - 3.europe.pool.ntp.org
  roles:
    - stafwag.ntpd
```

## License

MIT/BSD

## Author Information

Created by Staf Wagemakers, email: staf@wagemakers.be, website: https://www.wagemakers.be, my company https://mask27.dev
