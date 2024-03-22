# Establish_a_network_plan

### IP ADRESSING TABLE

## Server

DHCP server => 192.168.1.3
Active Directory/DNS server => 192.168.1.4
iSCSI storage/RADIUS server => 192.168.1.5

## Management / VLAN 10 192.168.3.0/27 

PC 1 => 192.168.3.11
PC 2 => 192.168.3.12
PC 3 => 192.168.3.13
PC 4 => 192.168.3.14
PC 5 => 192.168.3.15

## Study / VLAN 20 192.168.4.0/27

PC 1 => 192.168.4.11
PC 2 => 192.168.4.12
PC 3 => 192.168.4.13
PC 4 => 192.168.4.14
PC 5 => 192.168.4.15
PC 6 => 192.168.4.16
PC 7 => 192.168.4.17
PC 8 => 192.168.4.18

## Support / VLAN 30 192.168.5.0/26

PC 1 => 192.168.5.11
PC 2 => 192.168.5.12
PC 3 => 192.168.5.13
PC 4 => 192.168.5.14
PC 5 => 192.168.5.15
PC 6 => 192.168.5.16
PC 7 => 192.168.5.17
PC 8 => 192.168.5.18
PC 9 => 192.168.5.19
PC 10 => 192.168.5.20
PC 11 => 192.168.5.21
PC 12 => 192.168.5.22
PC 13 => 192.168.5.23
PC 14 => 192.168.5.24
PC 15 => 192.168.5.25
PC 16 => 192.168.5.26
PC 17 => 192.168.5.27
PC 18 => 192.168.5.28
PC 19 => 192.168.5.29
PC 20 => 192.168.5.30

### Configuration Details

# Router1

Entry of the network 192.168.1.0

A switch is connected with 3 server to this router;
    => Server DHCP
    => Server Active Directory / DNS
    => Server iSCSI / RADIUS

there is a connection with the Router2 where all VLAN is connected.


# Router2

- Router-on-a-Stick 
    => Network configuration where a single physical router interface is used to route traffic between multiple virtual LANs

=> Gig0/1.10 => 192.168.3.0 (VLAN10 / Management)
=> Gig0/1.20 => 192.168.4.0 (VLAN20 / Study)
=> Gig0/1.30 => 192.168.5.0 (VLAN30 / Support)

# Multi layer Switch 

- default route to Router2 
- IP route => can manage the traffic between different VLAN, so the traffic doesnt need to go up to the router2
    VLAN 10 => 192.168.3/27
    VLAN 20 => 192.168.4/27
    VLAN 30 => 192.168.5/26


### Security measures

# Both router are protected by RADIUS:

What radius does =>
1) Reduced risk of credential compromise if a network device is compromised.
2) Stronger password policies can be enforced by the RADIUS server.
3) Centralized management of user accounts and permissions.

# ACL

Protecting Server from the outside network



### Cost breakdown

2x Router 911 = 1700€ (850€ each)
1x Switch 3560-24PS layer 3 = 1500€
4x Switch 2950T-24 = 2200€ (550€ each)
1x Switch 2960-24TT = 1500€
3x Server = 6000€ (2000€ each)

Total cost = 12 900€

33x Computers = 33 000€
