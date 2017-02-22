lighttpd-static
===============

Build
-----

```
lxdfile build lighttpd-static
```

Launch
------

You can copy your static website into the container using the `configure.inject` script.

```
lxdfile launch lighttpd-static static -i configure.inject
```
