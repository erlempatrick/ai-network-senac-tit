No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 24.04.4 LTS
Release:        24.04
Codename:       noble
---

PRETTY_NAME="Ubuntu 24.04.4 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04.4 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"      
UBUNTU_CODENAME=noble
LOGO=ubuntu-logo
---

Linux ctlinux01 6.8.0-107-generic #107-Ubuntu SMP PREEMPT_DYNAMIC Fri Mar 13 19:51:50 UTC 2026 x86_64 x86_64 x86_64 GNU/Linux
---

23:27:55 up  1:58, 10 users,  load average: 0.01, 0.00, 0.00
---

               total        used        free      shared  buff/cache   available
Mem:            3915         589        2930           1         615        3326
Swap:           3914           0        3914
---

NAME                      MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
sda                         8:0    0   50G  0 disk 
├─sda1                      8:1    0    1M  0 part 
├─sda2                      8:2    0    2G  0 part /boot
└─sda3                      8:3    0   48G  0 part
  └─ubuntu--vg-ubuntu--lv 252:0    0   48G  0 lvm  /
sr0                        11:0    1 1024M  0 rom
---

Filesystem                         Size  Used Avail Use% Mounted on
tmpfs                              392M  1.3M  391M   1% /run
/dev/mapper/ubuntu--vg-ubuntu--lv   47G  8.5G   37G  19% /
tmpfs                              2.0G     0  2.0G   0% /dev/shm
tmpfs                              5.0M     0  5.0M   0% /run/lock
/dev/sda2                          2.0G  200M  1.6G  11% /boot
tmpfs                              392M   12K  392M   1% /run/user/1001
tmpfs                              392M   12K  392M   1% /run/user/1008
tmpfs                              392M   12K  392M   1% /run/user/1005
tmpfs                              392M   12K  392M   1% /run/user/1009
tmpfs                              392M   12K  392M   1% /run/user/1004
tmpfs                              392M   12K  392M   1% /run/user/1011
tmpfs                              392M   12K  392M   1% /run/user/1002
tmpfs                              392M   12K  392M   1% /run/user/1012
tmpfs                              392M   12K  392M   1% /run/user/1006
tmpfs                              392M   12K  392M   1% /run/user/1013
---

 Static hostname: ctlinux01
       Icon name: computer-vm
         Chassis: vm 🖴
      Machine ID: 05c2865e767d44c4870777b482ba0652
         Boot ID: a5a81cd031274f22b58fcf4ab580cf85
  Virtualization: oracle
Operating System: Ubuntu 24.04.4 LTS
          Kernel: Linux 6.8.0-107-generic
    Architecture: x86-64
 Hardware Vendor: innotek GmbH
  Hardware Model: VirtualBox
Firmware Version: VirtualBox
   Firmware Date: Fri 2006-12-01
    Firmware Age: 19y 6month       
---

1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:42:90:a5 brd ff:ff:ff:ff:ff:ff
    inet 10.24.82.200/24 brd 10.24.82.255 scope global enp0s3
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe42:90a5/64 scope link
       valid_lft forever preferred_lft forever
3: docker0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default
    link/ether 4e:15:bd:3d:de:85 brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever
    inet6 fe80::4c15:bdff:fe3d:de85/64 scope link
       valid_lft forever preferred_lft forever
4: veth1321de1@if2: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master docker0 state UP group default
    link/ether 4a:c1:39:f7:48:f4 brd ff:ff:ff:ff:ff:ff link-netnsid 0
    inet6 fe80::48c1:39ff:fef7:48f4/64 scope link
       valid_lft forever preferred_lft forever
---

default via 10.24.82.1 dev enp0s3 proto static
10.24.82.0/24 dev enp0s3 proto kernel scope link src 10.24.82.200
172.17.0.0/16 dev docker0 proto kernel scope link src 172.17.0.1
---

Global
         Protocols: -LLMNR -mDNS -DNSOverTLS DNSSEC=no/unsupported
  resolv.conf mode: stub

Link 2 (enp0s3)
    Current Scopes: DNS
         Protocols: +DefaultRoute -LLMNR -mDNS -DNSOverTLS DNSSEC=no/unsupported
Current DNS Server: 8.8.4.4
       DNS Servers: 8.8.8.8 8.8.4.4

Link 3 (docker0)
    Current Scopes: none
         Protocols: -DefaultRoute -LLMNR -mDNS -DNSOverTLS DNSSEC=no/unsupported

Link 4 (veth1321de1)
    Current Scopes: none
         Protocols: -DefaultRoute -LLMNR -mDNS -DNSOverTLS DNSSEC=no/unsupported
---

State              Recv-Q              Send-Q                           Local Address:Port                           Peer Address:Port             Process
LISTEN             0                   4096                                127.0.0.54:53                                  0.0.0.0:*
LISTEN             0                   4096                                   0.0.0.0:22                                  0.0.0.0:*
LISTEN             0                   4096                             127.0.0.53%lo:53                                  0.0.0.0:*
LISTEN             0                   4096                                   0.0.0.0:9000                                0.0.0.0:*
LISTEN             0                   4096                                      [::]:9000                                   [::]:*
---

  UNIT                        LOAD   ACTIVE SUB     DESCRIPTION                                   
  containerd.service          loaded active running containerd container runtime
  cron.service                loaded active running Regular background program processing daemon
  dbus.service                loaded active running D-Bus System Message Bus
  docker.service              loaded active running Docker Application Container Engine
  fwupd.service               loaded active running Firmware update daemon
  getty@tty1.service          loaded active running Getty on tty1
  ModemManager.service        loaded active running Modem Manager
  multipathd.service          loaded active running Device-Mapper Multipath Device Controller
  polkit.service              loaded active running Authorization Manager
  portainer.service           loaded active running Portainer container
  rsyslog.service             loaded active running System Logging Service
  ssh.service                 loaded active running OpenBSD Secure Shell server
  systemd-hostnamed.service   loaded active running Hostname Service
  systemd-journald.service    loaded active running Journal Service
  systemd-logind.service      loaded active running User Login Management
  systemd-networkd.service    loaded active running Network Configuration
  systemd-resolved.service    loaded active running Network Name Resolution
  systemd-timesyncd.service   loaded active running Network Time Synchronization
  systemd-udevd.service       loaded active running Rule-based Manager for Device Events and Files
  udisks2.service             loaded active running Disk Manager
  unattended-upgrades.service loaded active running Unattended Upgrades Shutdown
  upower.service              loaded active running Daemon for power management
  user@1001.service           loaded active running User Manager for UID 1001
  user@1002.service           loaded active running User Manager for UID 1002
---

Listing... Done
binutils-common/noble-updates 2.42-4ubuntu2.10 amd64 [upgradable from: 2.42-4ubuntu2.8]
binutils-x86-64-linux-gnu/noble-updates 2.42-4ubuntu2.10 amd64 [upgradable from: 2.42-4ubuntu2.8]
binutils/noble-updates 2.42-4ubuntu2.10 amd64 [upgradable from: 2.42-4ubuntu2.8]
containerd.io/noble 2.2.2-1~ubuntu.24.04~noble amd64 [upgradable from: 2.2.1-1~ubuntu.24.04~noble]
coreutils/noble-updates 9.4-3ubuntu6.2 amd64 [upgradable from: 9.4-3ubuntu6.1]
docker-buildx-plugin/noble 0.33.0-1~ubuntu.24.04~noble amd64 [upgradable from: 0.31.1-1~ubuntu.24.04~noble]
docker-ce-cli/noble 5:29.4.0-1~ubuntu.24.04~noble amd64 [upgradable from: 5:29.2.1-1~ubuntu.24.04~noble]
docker-ce-rootless-extras/noble 5:29.4.0-1~ubuntu.24.04~noble amd64 [upgradable from: 5:29.2.1-1~ubuntu.24.04~noble]
docker-ce/noble 5:29.4.0-1~ubuntu.24.04~noble amd64 [upgradable from: 5:29.2.1-1~ubuntu.24.04~noble]
docker-compose-plugin/noble 5.1.1-1~ubuntu.24.04~noble amd64 [upgradable from: 5.1.0-1~ubuntu.24.04~noble]
fwupd/noble-updates 1.9.34-0ubuntu1~24.04.1 amd64 [upgradable from: 1.9.33-0ubuntu1~24.04.1ubuntu1]
libbinutils/noble-updates 2.42-4ubuntu2.10 amd64 [upgradable from: 2.42-4ubuntu2.8]      
libctf-nobfd0/noble-updates 2.42-4ubuntu2.10 amd64 [upgradable from: 2.42-4ubuntu2.8]    
14]
libsystemd0/noble-updates 255.4-1ubuntu8.15 amd64 [upgradable from: 255.4-1ubuntu8.14]
libudev1/noble-updates 255.4-1ubuntu8.15 amd64 [upgradable from: 255.4-1ubuntu8.14]
linux-base/noble-updates 4.5ubuntu9+24.04.2 all [upgradable from: 4.5ubuntu9+24.04.1]
lshw/noble-updates 02.19.git.2021.06.19.996aaad9c7-2ubuntu0.24.04.1 amd64 [upgradable from: 02.19.git.2021.06.19.996aaad9c7-2build3]
netplan-generator/noble-updates 1.1.2-8ubuntu1~24.04.2 amd64 [upgradable from: 1.1.2-8ubuntu1~24.04.1]
netplan.io/noble-updates 1.1.2-8ubuntu1~24.04.2 amd64 [upgradable from: 1.1.2-8ubuntu1~24.04.1]
nftables/noble-updates 1.0.9-1ubuntu0.1 amd64 [upgradable from: 1.0.9-1build1]
python3-netplan/noble-updates 1.1.2-8ubuntu1~24.04.2 amd64 [upgradable from: 1.1.2-8ubuntu1~24.04.1]
sosreport/noble-updates 4.10.2-0ubuntu0~24.04.1 amd64 [upgradable from: 4.9.2-0ubuntu0~24.04.1]
systemd-dev/noble-updates 255.4-1ubuntu8.15 all [upgradable from: 255.4-1ubuntu8.14]
systemd-resolved/noble-updates 255.4-1ubuntu8.15 amd64 [upgradable from: 255.4-1ubuntu8.14]
systemd-sysv/noble-updates 255.4-1ubuntu8.15 amd64 [upgradable from: 255.4-1ubuntu8.14]
systemd-timesyncd/noble-updates 255.4-1ubuntu8.15 amd64 [upgradable from: 255.4-1ubuntu8.14]
systemd/noble-updates 255.4-1ubuntu8.15 amd64 [upgradable from: 255.4-1ubuntu8.14]
ubuntu-drivers-common/noble-updates 1:0.9.7.6ubuntu3.6 amd64 [upgradable from: 1:0.9.7.6ubuntu3.5]
udev/noble-updates 255.4-1ubuntu8.15 amd64 [upgradable from: 255.4-1ubuntu8.14]
aluno05@ctlinux01:~$