# enp1s0_to_eth0_in_Ubuntu

### First step is to install tools to configure network interfaces
```bash
$ sudo apt update
$ sudo apt install ifupdown net-tools
```

### Next, change from current enp0s3 to old network interfaces naming convention eth0. To do so with administrative privileges edit the /etc/default/grub file anf change the following line:
```bash
FROM:
GRUB_CMDLINE_LINUX=""
TO:
GRUB_CMDLINE_LINUX="net.ifnames=0 biosdevname=0"
```

### Once ready update Grub with:
```bash
$ sudo update-grub
```

### Reboot your system:
```bash
$ sudo reboot
```

**Note:**Make sure you have already done entries in the /etc/netplan/00-___.yml file
