lxdfile-examples
================

Examples of lxdfiles. See the main [lxdfile](https://github.com/hverr/lxdfile) repository.

Example usage:

```
git clone https://github.com/henri/lxdfile-examples
cd lxdfile-examples/gogs
lxc image copy images:ubuntu/yakkety/amd64 local: --copy-aliases --auto-update
lxdfile build gogs
lxdfile launch gogs gogs

```
