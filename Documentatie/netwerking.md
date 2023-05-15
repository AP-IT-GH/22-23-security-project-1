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
- VLAN150: 10.126.0.3
- VLAN140: 10.126.0.4
- VLANGuest: 10.126.0.5

DC: 10.126.0.10 DG: 10.126.0.3 
server: 10.126.0.12 DG: 10.126.0.3
