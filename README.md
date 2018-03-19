# linux-udev-network-modify
Change the network interface name on linux from ens160 to eth0


We should change the network interface name ens160 to eth0 using the udev
[udev](https://en.wikipedia.org/wiki/Udev)


On Ubuntu 16.04  
```
/etc/udev/rules.d/70-persistent-net.rules
```
List network devices

```
networkctl
```

Get MAC address from a device

```
cat /sys/class/net/eth0/address
 
```

Add the following line
```
SUBSYSTEM=="net", ACTION=="add", DRIVERS=="?*", ATTR{address}=="02:01:02:03:04:05", ATTR{dev_id}=="0x0", ATTR{type}=="1", NAME="eth0"
```
Please, not forget subtitute 02:01:02:03:04:05 to your MAC address.
