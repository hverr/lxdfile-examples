easyrsa-ca
==========

This container contains the Easy-RSA v3 Certificate Authority utilities for managing an RSA Certificate Authority.

Installation
------------

After launching the container, enter the container with `bash`, and initialize the CA with the following commands:

```
cd /usr/share/easy-rsa
./easyrsa build-ca
```

Signing a server certificate
----------------------------

Sign requests by pushing the `*.req` file to the container. Then enter the container with `bash` and execute the following commands:

```
cd /usr/share/easy-rsa
./easyrsa import-req /path/to/received.req UNIQUE_SHORT_FILE_NAME
./easyrsa show-req UNIQUE_SHORT_FILE_NAME
./easyrsa sign server UNIQUE_SHORT_FILE_NAME
```

Now pull the signed certificate from the container, and use it at the server side.

Signing a client certificate
----------------------------

Sign requests by pushing the `*.req` file to the container. Then enter the container with `bash` and execute the following commands:

```
cd /usr/share/easy-rsa
./easyrsa import-req /path/to/received.req UNIQUE_SHORT_FILE_NAME
./easyrsa show-req UNIQUE_SHORT_FILE_NAME
./easyrsa sign client UNIQUE_SHORT_FILE_NAME
```

Now pull the signed certificate from the container, and use it at the client side.
