nagios
======

Contains Nagios Core, served by lighttpd.

Launch
------

Edit the `nagiosadmin` password in the `passwd` file.

```
lxdfile build nagios
lxdfile launch nagios nagios -i configure.inject
```
