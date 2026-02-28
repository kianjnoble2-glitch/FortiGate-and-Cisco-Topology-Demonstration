# FortiGate-and-Cisco-Topology-Demonstration
This project aims to demonstrate the skills I've acquired while studying Fortinet's FortiGate courses as well as Cisco's CCNA (and further).

V2:
Tests OSPF peerings using GRE over IPsec and (separately) Route-based IPsec tunnels (VTI). Forti-1 and Forti-3 have an OSPF peering using VTI tunnel alone. R1 and R2 have peering using GRE over IPsec.
The tunnel interfaces of Forti-1 and Forti-3 are 10.255.255.1/30
and 10.255.255.2/30 respectively. The GRE tunnel interfaces of
R1 and R2 are 10.255.255.5/30 and 10.255.255.6/30 
respectively.

The GRE tunnel can be removed and OSPF neighbour peerings
can be formed directly between R1->Forti-1->Forti-3->R2 with no
issues. The purpose was to test OSPF across the GRE and VTI
tunnels.

V1:
The external network makes use of the NAT node adapter in
VMWare settings configuration.

This lab simulation makes use of an evaluation-licensed
FortiGate v7.2.0 KVM. Some features may not be available.

---------------------------------------------------------------------

The included ".gns3project" files include the topology as well as the images.

---------------------------------------------------------------------

The internal network subnet corresponds to: 10.0.0.0/24
The external network subnet corresponds to: 192.168.233.0/24 

SSL Deep Inspection is enabled, install the browser certificate
in virtual devices to avoid certificate errors.

Application control monitors high bandwith activity (to enable
testing internet connectivity/functionality via YouTube, etc).

FortiGuard outbreak prevention database is unavailable for
evaluation licenses.

FortiGuard category based filtering is unavailable for evaluation
licenses.

For FortiGate High Availability (HA), Fortigate Forti-1 is the
primary firewall. FortiGate Forti-2 is the secondary firewall. High
Availability (HA) is only configured in HQ.

LAG is configured between Forti-1 and Forti-2 using ports 8 & 9.
Ports 7 between Forti-1 and Forti-2 are used as heartbeat
interfaces for FortiGate High Availability (HA). They do not have
IP addresses. The HA mode is 'Active-Passive'.

---------------------------------------------------------------------

Where applicable, all usernames are: 'admin', all pw are: '123'.
IPsec VPN pw is: 'forti-ipsec'.
FortiGate HA pw is: 'forti-ha', group name is: 'HQ-HA'.
WAN-facing IPs are as follows:
Forti-1: 192.168.233.100
Forti-2: 192.168.233.101 (before HA)
Forti-3: 192.168.233.200
Cloud ISPs: 192.168.233.2 (automatically assigned by GNS3)
