postgresql
==========

Build
-----

```
lxdfile build postgresql
```

Launch
------

Edit `configure.inject` to setup the user and database name.

```
lxdfile launch postgresql postgresql -i configure.inject
```

The user password should be echoed to standard output.
