# Netwerking

We hebben het netwerk opgedeeld in 3 delen, een deel voor de servers, een deel voor de gemeentemedewerkers en een gast gedeelte.

Er zijn 3 subnetwerken:
1. Vlan 150 wordt gebruikt voor de server en de domain controller.
2. Vlan 140 wordt gebruikt voor de gemeente medewerkers.
3. Het derde netwerk is voor gast gebruikers.

## VLAN lijst


## Ip adressen
- Domain controller: 10.126.0.10 192.168.254.10 DG 192.168.254.250
- Pfsense: 10.126.0.1
- Server: 10.126.0.5 192.168.254.12
- Default gateway: 10.126.0.1

## Netwerk Design
- VLAN150: 192.168.254.250
- VLAN140: 192.168.250.250
- VLANGuest: 192.168.248.250

### Domain Controller:
- Vlan150
- Static IP: 192.168.254.1
- Default Gateway: 192.168.254.250
#### DHCP range
- Start: 192.168.0.1
- End: 192.168.3.254
- Netmask: /22 (255.255.252.0)
### Server
- Vlan150
- Static IP: 192.168.254.2
- Default Gateway: 192.168.254.250

### Clients
- Vlan140
- Dynamic IP: DHCP

