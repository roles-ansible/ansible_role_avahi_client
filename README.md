 ansible role avahi_client
===========================

Avahi provides local hostname resolution using a "hostname.local" naming scheme.
This ansible role installs the required dependencies and configures the DNS resolver accordingly.

You can opt-out from deploying a new ``/etc/nsswitch.conf`` config by setting ``avahi__configure_nsswitch`` to ``false``.

You can opt-in in a simple versionscheck that can prevent you from running a older version of this role by setting ``submodules_versioncheck`` to ``true``.

 Learn more
------------
+ [/etc/nsswitch.conf](https://man7.org/linux/man-pages/man5/nsswitch.conf.5.html)
+ Avahi [wiki.archlinux.org](https://wiki.archlinux.org/title/Avahi)
