http://localhost:5000/svg/l3d.avahi_client.svg

[![Ansible Galaxy](https://ansible.l3d.space/svg/l3d.avahi_client.svg)](https://galaxy.ansible.com/l3d/avahi_client)
[![BSD-3 Clause](https://ansible.l3d.space/svg/l3d.avahi_client_license.svg)](LICENSE)
[![Maintainance](https://ansible.l3d.space/svg/l3d.avahi_client_maintainance.svg)](https://ansible.l3d.space/#l3d.avahi_client)

 ansible role avahi_client
===========================

Avahi provides local hostname resolution using a "hostname.local" naming scheme.
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


Learn more
----------

* DNS-SD [http://dns-sd.org/](http://dns-sd.org/)
* mDNS [http://www.multicastdns.org/](http://www.multicastdns.org/)

* Avahi [https://www.avahi.org/](https://www.avahi.org/)
* Avahi git [https://github.com/lathiat/avahi](https://github.com/lathiat/avahi)
* Avahi [wiki.archlinux.org](https://wiki.archlinux.org/title/Avahi)

* [NSS mdns plugin](https://github.com/lathiat/nss-mdns)
* [/etc/nsswitch.conf](https://manpages.debian.org/unstable/manpages/nsswitch.conf.5.en.html)
