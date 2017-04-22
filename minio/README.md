Minio - S3 compatible object store
==================================

Packages [minio](https://github.com/minio/minio), an S3 compatible object store with a web interface.

Build
-----

```
lxdfile build minio
```

Launch
------
```
lxdfile launch minio minio
lxc exec minio -- systemctl status minio.service
```

The last command should output the API key.
