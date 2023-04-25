[![Ansible Galaxy](https://ansible.l3d.space/svg/l3d.avahi_client.svg)](https://galaxy.ansible.com/l3d/avahi_client)
[![MIT License](https://ansible.l3d.space/svg/l3d.avahi_client_license.svg)](LICENSE)
[![Maintainance](https://ansible.l3d.space/svg/l3d.avahi_client_maintainance.svg)](https://ansible.l3d.space/#l3d.avahi_client)

 ansible role avahi_client
===========================

Avahi provides local hostname resolution using the ``.local`` MDNS Domain.
This ansible role installs the required dependencies and configures the DNS resolver accordingly.

You can opt-out from deploying a new ``/etc/nsswitch.conf`` config by setting ``avahi_client__configure_nsswitch`` to ``false``.

You can opt-in in a simple versionscheck that can prevent you from running a older version of this role by setting ``submodules_versioncheck`` to ``true``.


 Configuring nsswitch
--------------------

If you want only IPv4 or IPv6 names resolved, change ``mdns`` to ``mdns4`` or ``mdns6`` in these variables:

```yaml
avahi_client__mdns_name: 'mdns'
avahi_client__mdns_minimal_name: 'mdns_minimal'
```

From the documentation of [nss-mdns](https://github.com/lathiat/nss-mdns)

> `mdns` resolves both IPv6 and IPv4 addresses, `mdns4` only IPv4 addresses and `mdns6` only IPv6 addresses.
> `mdns{4,6,}_minimal` is mostly identical to the versions without `_minimal`. However, they differ in one way. The minimal versions will always deny to resolve host names that don't end in `.local` or addresses that aren't in the range `169.254.x.x` (the range used by IPV4LL/APIPA/RFC3927.)
> Combining the `_minimal` and the normal NSS modules allows us to make mDNS authoritative for Zeroconf host names and addresses and use it as fallback for everything else.


 Ansible Collection
--------------------
This role is part of the ``l3d.avahi`` Ansible Collection.

[![collection l3d.avahi](https://ansible.l3d.space/svg/l3d.avahi_ansible-collection_collection.svg)](https://galaxy.ansible.com/l3d/avahi)
[![Maintainance](https://ansible.l3d.space/svg/l3d.avahi_maintainance_collection.svg)](https://ansible.l3d.space/#l3d.avahi)
[![License](https://ansible.l3d.space/svg/l3d.avahi_license_collection.svg)](LICENSE)

Visit the [README.md](https://github.com/roles-ansible/ansible_collection_avahi#readme) of the l3d.avahi collection for information about downloading or integrating the collection to your ansible playbook.

### Role Usage Example:
```bash
# ansible-galaxy install l3d.avahi_client

- name: "Let your System use MDNS to resolve .local addresses"
  hosts: localhost
  roles:
    - {role: l3d.avahi_client, tags: avahi}
  vars:
    # Enable optional Versioncheck.
    submodules_versioncheck: true
```

 Learn more
----------

* DNS-SD [http://dns-sd.org/](http://dns-sd.org/)
* mDNS [http://www.multicastdns.org/](http://www.multicastdns.org/)

* Avahi [https://www.avahi.org/](https://www.avahi.org/)
* Avahi git [https://github.com/lathiat/avahi](https://github.com/lathiat/avahi)
* Avahi [wiki.archlinux.org](https://wiki.archlinux.org/title/Avahi)

* [NSS mdns plugin](https://github.com/lathiat/nss-mdns)
* [/etc/nsswitch.conf](https://manpages.debian.org/unstable/manpages/nsswitch.conf.5.en.html)
