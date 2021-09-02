[![Galaxy](https://github.com/roles-ansible/ansible_role_avahi_client/raw/main/.github/galaxy.svg)](https://galaxy.ansible.com/do1jlr/avahi_client)
[![License](https://github.com/roles-ansible/ansible_role_avahi_client/raw/main/.github/license.svg)](https://github.com/roles-ansible/ansible_role_avahi_client/blob/main/LICENSE)

 ansible role avahi_client
===========================

Avahi provides local hostname resolution using a "hostname.local" naming scheme.
This ansible role installs the required dependencies and configures the DNS resolver accordingly.

You can opt-out from deploying a new ``/etc/nsswitch.conf`` config by setting ``avahi__configure_nsswitch`` to ``false``.

You can opt-in in a simple versionscheck that can prevent you from running a older version of this role by setting ``submodules_versioncheck`` to ``true``.

If you want only IPv4 or IPv6 names resolved, change ``mdns`` to ``mdns4`` or ``mdns6`` in these variables:
```yaml
avahi__mdns_name: 'mdns'
avahi__mdns_minimal_name: 'mdns_minimal'
```

 Learn more
------------
+ [/etc/nsswitch.conf](https://man7.org/linux/man-pages/man5/nsswitch.conf.5.html)
+ Avahi [wiki.archlinux.org](https://wiki.archlinux.org/title/Avahi)
+ nss-mdns [0pointer.de](https://0pointer.de/lennart/projects/nss-mdns/#documentation)
