sonarqube
=========

Build
-----

```
lxdfile build sonarqube
```

Launch
------

Configure `sonar.properties` using appropriate values

```
lxdfile launch sonarqube sonarqube -i configure.inject
```

SonarQube is now listening on port 9000.

Plugins
-------

To install plugins see the [`plugins/`](plugins/#readme) directory.
