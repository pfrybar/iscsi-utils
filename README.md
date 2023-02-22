## iscsi-utils

A couple of scripts to help login/mount and unmount/logout of iscsi targets.

### Why?

`iscsiadm` mounts a target as one or more block devices on the client. It's up to
the client's OS to give these devices a name/location. In order to discover the
device(s), most documentation recommends to look at the output from `dmesg` or
try to find the device in '/dev/disk/by-path'. While parsing '/dev/disk/by-path'
could be scripted (and there are some tools that do this), not all Linux systems
expose devices this way (looking at you Synology).

`mount-iscsi.sh` gets around this limitation by using the UUID and passing this
to `mount`. Once you partition the disk(s) the way you want, it's easy to use
this script to login and mount all necessary partions.
