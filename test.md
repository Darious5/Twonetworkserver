# status of isc-dhcp-server
vagrant@dhcp:~$ systemctl status isc-dhcp-server.service 
● isc-dhcp-server.service - LSB: DHCP server
     Loaded: loaded (/etc/init.d/isc-dhcp-server; generated)
     Active: active (running) since Fri 2024-11-15 19:00:01 UTC; 14min ago
       Docs: man:systemd-sysv-generator(8)
    Process: 14067 ExecStart=/etc/init.d/isc-dhcp-server start (code=exited, status=0/SUCCESS)
      Tasks: 1 (limit: 2308)
     Memory: 4.1M
        CPU: 31ms
     CGroup: /system.slice/isc-dhcp-server.service
             └─14079 /usr/sbin/dhcpd -4 -q -cf /etc/dhcp/dhcpd.conf eth2 eth3
# ip of switch 1
3: eth1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:1a:a0:e8:c2:39 brd ff:ff:ff:ff:ff:ff
    altname enp0s8
    inet 192.168.57.101/24 brd 192.168.57.255 scope global dynamic eth1
       valid_lft 43019sec preferred_lft 43019sec
    inet6 fe80::21a:a0ff:fee8:c239/64 scope link 
       valid_lft forever preferred_lft forever
# ip of switch 2
3: eth1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:1a:a0:e6:09:4a brd ff:ff:ff:ff:ff:ff
    altname enp0s8
    inet 192.168.58.200/24 brd 192.168.58.255 scope global dynamic eth1
       valid_lft 43032sec preferred_lft 43032sec
    inet6 fe80::21a:a0ff:fee6:94a/64 scope link 
       valid_lft forever preferred_lft forever
# ip of client 1
3: eth1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:1a:a0:e5:f5:d2 brd ff:ff:ff:ff:ff:ff
    altname enp0s8
    inet 192.168.57.200/24 brd 192.168.57.255 scope global dynamic eth1
       valid_lft 43150sec preferred_lft 43150sec
    inet6 fe80::21a:a0ff:fee5:f5d2/64 scope link 
       valid_lft forever preferred_lft forever
# ip of client 2
3: eth1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:1a:a0:e9:06:cf brd ff:ff:ff:ff:ff:ff
    altname enp0s8
    inet 192.168.58.102/24 brd 192.168.58.255 scope global dynamic eth1
       valid_lft 43148sec preferred_lft 43148sec
    inet6 fe80::21a:a0ff:fee9:6cf/64 scope link 
       valid_lft forever preferred_lft forever
