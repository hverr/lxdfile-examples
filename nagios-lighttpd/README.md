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

Extras
------

Also contains the [go-smtp-send](https://github.com/hverr/go-smtp-send) utility to easily send mails using SMTP.

  - The utility is installed in `/usr/local/nagios/libexec/go-smtp-send`.
  - The utility requires a configuration file in `/etc/go-smtp-send.yaml` (see above link).
  - An inject script can be used to inject the configuration file.
