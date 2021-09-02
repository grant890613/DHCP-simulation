# DHCP-simulation
This is a simple DHCP simulation

Environment setup:

$ sudo apt install isc dhcp server y
$ sudo apt install isc dhcp client y
$ sudo apt install traceroute y
#Modify AppArmor settings
$ sudo ln s /etc/apparmor.d/usr.sbin.dhcpd /etc/apparmor.d
$ sudo apparmor_parser -R /etc/apparmor.d/usr.sbin.dhcpd
$ sudo /etc/init.d/apparmor stop
$ sudo sed i '30i / var / dhcp {, dhcpclient * lrw ,' /etc/apparmor.d/sbin.dhclient

#Run the simulation
$ sudo python topology.py

*You can modify the dhcpd.conf to change IP pool
