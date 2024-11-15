In this practice we configured a DHCP server to give ips to the clients in two different subnets,
in order to do that, we made a Vagrant file that creates the machines for the DHCP server, the two switches, 
and the two clients of each subnet, in the exercise there are 3 clients per subnet but to simplify the exercise
we just made one for each subnet, we configured locally the dhcpd.conf and the isc-dhcp-server in order to 
then use vagrant provision to copy each file where it should belong inside the DHCP server in order for it 
to function perfectly, all the test done in order to see if it works are made in a file called test.md
Because of Vagrant limitations, we cant get the ips that are prompted by the exercies, instead, we have to use
ips that range from 56-58 in this case. The tests failed at first because i was using libvirt provider instead 
of virtualbox while using virtualbox__intnets, which made it unusable, and made it so the vms werent connecting 
to the correct intnets and, therefore, the dhcp server was unable to assign any ips at all, i changed the 
provider to virtual box and now it works, also, i had an older version of vagrant so i thought about using 
virtualbox 6, but it didnt worked, i upgraded both vagrant and virtualbox to the lastest version, i have seen 
that they have problems with each other so i downgraded virtualbox to 7.0 and now it works without issues in 
the vagrant/vbox side. the clients didnt worked properly so i upgraded their specs so they work without any
problems
and as we can see in test.md, the DHCP server works perfectly, keep in mind that we didnt used the original
ips from the exercise because vagrant cannot use them, but using other ips and being as truthful as i can
to the original exercise considering vagrant limitations, i made it work.
