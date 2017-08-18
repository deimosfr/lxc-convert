This repository is not maintained anymore. Only pull requests are accepted

lxc-convert
===========

Convert a Debian physical/VM to an LXC container

Usage
-----
To use it, it's easy. First of all mount or copy all your datas in the rootfs folder, be sure to have enough space, then launch the lxc-convert script like in this example:

```
migrated_container=migrated_container
mkdir -p /var/lib/lxc/$migrated_container/rootfs
rsync -e ssh -a --exclude '/dev' --exclude '/proc' --exclude '/sys' <old_vm>:/ /var/lib/lxc/$migrated_container/rootfs
lxc-convert -p /var/lib/lxc/$migrated_container -n $migrated_container
```

You can find more information on my wiki:
https://wiki.deimos.fr/LXC_:_Install_and_configure_the_Linux_Containers
