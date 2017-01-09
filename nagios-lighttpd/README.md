nagios
======

Contains Nagios Core, served by lighttpd.

Launch
------

1. Edit the `nagiosadmin` password in the `passwd` file.
2. Put server configurations in `etc/objects/servers/*.cfg`.
3. Run

```
lxdfile build nagios
lxdfile launch nagios nagios -i passwd.inject -i configure.inject
```
