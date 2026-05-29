wslinux01
---

senac@wslinux01:~$ lsb_release -a
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 24.04.4 LTS
Release:        24.04
Codename:       noble
---

1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:87:16:df brd ff:ff:ff:ff:ff:ff
    inet 10.24.82.214/24 brd 10.24.82.255 scope global enp0s3
       valid_lft forever preferred_lft forever
    inet 10.24.82.47/24 metric 100 brd 10.24.82.255 scope global secondary dynamic enp0s3
       valid_lft 27699sec preferred_lft 27699sec
---

default via 10.24.82.1 dev enp0s3 proto static
default via 10.24.82.1 dev enp0s3 proto dhcp src 10.24.82.47 metric 100
10.1.1.195 via 10.24.82.1 dev enp0s3 proto dhcp src 10.24.82.47 metric 100
10.1.1.242 via 10.24.82.1 dev enp0s3 proto dhcp src 10.24.82.47 metric 100
10.24.40.190 via 10.24.82.1 dev enp0s3 proto dhcp src 10.24.82.47 metric 100
10.24.82.0/24 dev enp0s3 proto kernel scope link src 10.24.82.214
10.24.82.1 dev enp0s3 proto dhcp scope link src 10.24.82.47 metric 100
---

Global
         Protocols: -LLMNR -mDNS -DNSOverTLS DNSSEC=no/unsupported
  resolv.conf mode: stub

Link 2 (enp0s3)
    Current Scopes: DNS
         Protocols: +DefaultRoute -LLMNR -mDNS -DNSOverTLS DNSSEC=no/unsupported
Current DNS Server: 8.8.8.8
       DNS Servers: 8.8.8.8 8.8.4.4 10.24.40.190 10.1.1.195 10.1.1.242
        DNS Domain: senac.br senacsp.edu.br
---

COMMAND    PID            USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
systemd      1            root  213u  IPv4   7583      0t0  TCP *:22 (LISTEN)
systemd-n  549 systemd-network   19u  IPv4  13765      0t0  UDP 10.24.82.47:68
systemd-r  562 systemd-resolve   14u  IPv4   7415      0t0  UDP 127.0.0.53:53
systemd-r  562 systemd-resolve   15u  IPv4   7416      0t0  TCP 127.0.0.53:53 (LISTEN)
systemd-r  562 systemd-resolve   16u  IPv4   7417      0t0  UDP 127.0.0.54:53
systemd-r  562 systemd-resolve   17u  IPv4   7418      0t0  TCP 127.0.0.54:53 (LISTEN)
node_expo  716   node_exporter    3u  IPv6   9397      0t0  TCP *:9100 (LISTEN)
node_expo  716   node_exporter    6u  IPv6  13252      0t0  TCP 127.0.0.1:9100->127.0.0.1:52354 (ESTABLISHED)
prometheu  724      prometheus    6u  IPv6  10281      0t0  TCP *:9091 (LISTEN)
prometheu  724      prometheus    8u  IPv6  13212      0t0  TCP 127.0.0.1:9091->127.0.0.1:46472 (ESTABLISHED)
prometheu  724      prometheus   11u  IPv4  13251      0t0  TCP 127.0.0.1:52354->127.0.0.1:9100 (ESTABLISHED)
prometheu  724      prometheus   16u  IPv4  13211      0t0  TCP 127.0.0.1:46472->127.0.0.1:9091 (ESTABLISHED)
apache2    756            root    3u  IPv4   7162      0t0  TCP *:80 (LISTEN)
apache2    756            root    4u  IPv4   7164      0t0  TCP *:8888 (LISTEN)
java       815          tomcat   44u  IPv6   7970      0t0  TCP *:8080 (LISTEN)
apache2    947        www-data    3u  IPv4   7162      0t0  TCP *:80 (LISTEN)
apache2    947        www-data    4u  IPv4   7164      0t0  TCP *:8888 (LISTEN)
apache2    948        www-data    3u  IPv4   7162      0t0  TCP *:80 (LISTEN)
apache2    948        www-data    4u  IPv4   7164      0t0  TCP *:8888 (LISTEN)
apache2    949        www-data    3u  IPv4   7162      0t0  TCP *:80 (LISTEN)
apache2    949        www-data    4u  IPv4   7164      0t0  TCP *:8888 (LISTEN)
apache2    953        www-data    3u  IPv4   7162      0t0  TCP *:80 (LISTEN)
apache2    953        www-data    4u  IPv4   7164      0t0  TCP *:8888 (LISTEN)
apache2    954        www-data    3u  IPv4   7162      0t0  TCP *:80 (LISTEN)
apache2    954        www-data    4u  IPv4   7164      0t0  TCP *:8888 (LISTEN)
mysqld     966           mysql   21u  IPv6   7973      0t0  TCP *:33060 (LISTEN)
mysqld     966           mysql   35u  IPv4  10288      0t0  TCP *:3306 (LISTEN)
grafana   1113         grafana   13u  IPv6  10314      0t0  TCP *:3000 (LISTEN)
sshd      1913            root    3u  IPv4   7583      0t0  TCP *:22 (LISTEN)
sshd      1915            root    4u  IPv4  14683      0t0  TCP 10.24.82.214:22->10.24.82.23:52755 (ESTABLISHED)
sshd      2017           senac    4u  IPv4  14683      0t0  TCP 10.24.82.214:22->10.24.82.23:52755 (ESTABLISHED)
---

