bryan 22 may

-> VLans zetten DHCP / DNS 
-> leases zetten excluden van de gateways enz
-> nakijken op test machines of vlans juist zijn geconfigureerd
-> pfsense VLANs allemaal aanmaken en juist zetten 
-> trunking juist zetten voor alle vlans



Voor alle vlans juist te zetten (vid)

https://www.virtualizationhowto.com/2021/05/windows-server-dhcp-vlan-configuration-detailed-guide/

B_Servers 
ip ->  192.168.254.10 (ip van windows host)

ip rangen -> 192.168.254.1 - 192.168.254.254

excludes  -> 
            
            192.168.254.250 -> gateway
            192.168.254.10 -> server windows

subnet /24 -> 255.255.255.0
gateway -> 192.168.254.250 

vlan 90
ip -> 

B_trunk
->> geen vlan nodig geen exclude mssch??



## B Servers 

windows AD name -> Thor
 -> installed AD DS function on the domain controller
 -> corp.vlavigem.com
 -> DSRM : uiopuiop123123!
 -> netbios name : vlavigem

excluded the 3 servers -> AD , kali en B_server
test Computer 

        -> Win11 Client check dhcp? yes
        -> Win11 Internet access? yes
        -> win11 forest configuration? -> ansible script voor schrijven

trunk staat aan 
## Vlan 140
netwerk voor client computers

hosts -> 1,022 (1,024)
full adres -> 192.168.248.0 /22
subnet /22 -> 255.255.252.0
usable hosts -> 192.168.248.1 - 192.168.251.254
gateway -> 192.168.250.250

    # juist zetten van de vlan in de pfsense
        - gateway adres juist zetten yes
        - range juist zetten in de vlan yes
        - taggen in pfsense yes

    # zetten van de vlan tag in de DHCP 
        - tag juist zetten in dhcp yes 
        - regels aanpassen yes
        - dns juist zetten bij de dhcp yes 

test Computer 

        -> Win11 Client check dhcp? yes
        -> Win11 Internet access?  yes
        -> win11 forest configuration? -> ansible script schrijven

## Vlan 
### script schrijven voor computers toe te voegen aan het netwerk Domain

## test sites
test Computer 

        -> Win11 Client check dhcp?
        -> Win11 Internet access? 
        -> win11 forest configuration?
## side commands

control option 2


## inorde
-   vlan voor servers DHCP 
-   vlan voor client setup
-   DHCP relay inorde gebracht
-   seperated vlan voor servers gecreerd


## netwerkschema 
