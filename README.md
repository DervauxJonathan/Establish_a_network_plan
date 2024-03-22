# IP Addressing Table

## Server

| Service                      | IP Address     |
|------------------------------|----------------|
| DHCP server                  | 192.168.1.3    |
| Active Directory/DNS server | 192.168.1.4    |
| iSCSI storage/RADIUS server  | 192.168.1.5    |

## Management / VLAN 10 (192.168.3.0/27)

| Device | IP Address   |
|--------|--------------|
| PC 1   | 192.168.3.11 |
| PC 2   | 192.168.3.12 |
| PC 3   | 192.168.3.13 |
| PC 4   | 192.168.3.14 |
| PC 5   | 192.168.3.15 |

## Study / VLAN 20 (192.168.4.0/27)

| Device | IP Address   |
|--------|--------------|
| PC 1   | 192.168.4.11 |
| PC 2   | 192.168.4.12 |
| PC 3   | 192.168.4.13 |
| PC 4   | 192.168.4.14 |
| PC 5   | 192.168.4.15 |
| PC 6   | 192.168.4.16 |
| PC 7   | 192.168.4.17 |
| PC 8   | 192.168.4.18 |

## Support / VLAN 30 (192.168.5.0/26)

| Device | IP Address   |
|--------|--------------|
| PC 1   | 192.168.5.11 |
| PC 2   | 192.168.5.12 |
| PC 3   | 192.168.5.13 |
| PC 4   | 192.168.5.14 |
| PC 5   | 192.168.5.15 |
| PC 6   | 192.168.5.16 |
| PC 7   | 192.168.5.17 |
| PC 8   | 192.168.5.18 |
| PC 9   | 192.168.5.19 |
| PC 10  | 192.168.5.20 |
| PC 11  | 192.168.5.21 |
| PC 12  | 192.168.5.22 |
| PC 13  | 192.168.5.23 |
| PC 14  | 192.168.5.24 |
| PC 15  | 192.168.5.25 |
| PC 16  | 192.168.5.26 |
| PC 17  | 192.168.5.27 |
| PC 18  | 192.168.5.28 |
| PC 19  | 192.168.5.29 |
| PC 20  | 192.168.5.30 |

## Configuration Details

### Router1
- Entry of the network: 192.168.1.0
- Connected Devices:
  - DHCP Server
  - Active Directory/DNS Server
  - iSCSI Storage/RADIUS Server

### Router2 (Router-on-a-Stick)
- Gig0/1.10 => VLAN 10 (192.168.3.0)
- Gig0/1.20 => VLAN 20 (192.168.4.0)
- Gig0/1.30 => VLAN 30 (192.168.5.0)

## Multi-layer Switch
- Default route to Router2
- IP Route:
  - VLAN 10 => 192.168.3/27
  - VLAN 20 => 192.168.4/27
  - VLAN 30 => 192.168.5/26

## Security Measures
- Both routers are protected by RADIUS, providing:
  1. Reduced risk of credential compromise if a network device is compromised.
  2. Stronger password policies enforced by the RADIUS server.
  3. Centralized management of user accounts and permissions.

## ACL
- Protecting Server from the outside network.

## Cost Breakdown
- 2x Router 911 = 1700€ (850€ each)
- 1x Switch 3560-24PS layer 3 = 1500€
- 4x Switch 2950T-24 = 2200€ (550€ each)
- 1x Switch 2960-24TT = 1500€
- 3x Server = 6000€ (2000€ each)
- Total cost = 12,900€

- 33x Computers = 33,000€
