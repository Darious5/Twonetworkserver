# status of isc-dhcp-server
vagrant@dhcp:~$ systemctl status isc-dhcp-server.service 
● isc-dhcp-server.service - LSB: DHCP server
     Loaded: loaded (/etc/init.d/isc-dhcp-server; generated)
     Active: active (running) since Thu 2024-11-14 17:28:22 UTC; 1min 18s ago
       Docs: man:systemd-sysv-generator(8)
    Process: 14956 ExecStart=/etc/init.d/isc-dhcp-server start (code=exited, status=0/SUCCESS)
      Tasks: 1 (limit: 496)
     Memory: 4.8M
        CPU: 22ms
     CGroup: /system.slice/isc-dhcp-server.service
             └─14968 /usr/sbin/dhcpd -4 -q -cf /etc/dhcp/dhcpd.conf eth2 eth3
# ip of switch 1
