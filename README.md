In this practice we configured a DHCP server to give ips to the clients in two different subnets,
in order to do that, we made a Vagrant file that creates the machines for the DHCP server, the two switches, 
and the two clients of each subnet, in the exercise there are 3 clients per subnet but to simplify the exercise
we just made one for each subnet, we configured locally the dhcpd.conf and the isc-dhcp-server in order to 
then use vagrant provision to copy each file where it should belong inside the DHCP server in order for it 
to function perfectly, all the test done in order to see if it works are made in a file called test.md
Because of Vagrant limitations, we cant get the ips that are prompted by the exercies, instead, we have to use
ips that range from 56-58 in this case.