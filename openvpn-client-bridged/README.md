openvpn-client-bridged
======================

Launching
---------

Edit `openvpn.conf` and launch the container:

```
lxdfile launch openvpn-client-bridged openvpn-client -i configure.inject
```

A tun device is needed. Make sure the container has access to the tun device:

```
modprobe tun
mkdir -p /dev/net
mknod /dev/net/tun c 10 200
lxc config device add openvpn-client tun unix-char path=/dev/net/tun
```

Setup
-----

### Keys
After launching the container, enter it using `bash`, then generate the client certificate:
```
cd /usr/share/easy-rsa
./easyrsa gen-req vpn-client nopass
```

This will generate a certificate request that has to be signed by your CA.

After signing, retrieve the CA certificate and the signed client certificate, use `lxdfile inject CONTAINER -i import_certs.inject` to inject the certificates. Inspect `import_certs.inject` to learn file name conventions.

### Bridge

Now connect the OpenVPN `tap0` device to your bridge, by configuring it in `/etc/network/interfaces`

```
auto tap0
iface tap0 inet manual
    pre-up ip tuntap add tap0 mode tap user root
    post-down ip link del dev tap0

auto vpn
iface vpn inet dhcp
    bridge_ports tap0 INTERFACE_WITH_DHCP
    bridge_stp off
    bridge_waitport 0
    bridge_fd 0
```

### Enable OpenVPN
Now enable OpenVPN `rc-update add openvpn` and restart the container.
