# Gebruikte OVA's en ISO's
Er wordt slechts gebruik gemaakt van drie verschillende OVA's; een voor de domain controller, een voor de server en een voor de firewall.

## Domain controller
De OVA van de domain controller bestaat uit een Windows Server 2019 installatie die een DHCP en DNS client bevat. Deze is voorzien van een vast IP adress en maakt gebruik van ntp server voor het accuraat houden van de systeem klok.  
  
DHCP is geconfigureerd op de AD met alle verschillende VLAN's in gedachten.  
DNS is geconfigureerd op de AD met een grote range zodat men een grote hoeveelheid apparaten kan deployen zonder problemen.

## Server
Deze bestaat uit een Ubuntu Server installatie waarop men docker op heeft geïnstalleerd. Deze staat klaar om gebruikt te worden als database en webserver voor de gemeente.

## Firewall
Deze bestaat uit een Pfsense installatie volledig geconfigureerd om de LAN en WAN kant te onderscheiden en beveiligen. We maken hier gebruik van een deny all policy, op die manier kan er niets binnen op de virtuele gemeente dat er niet moet zijn en maximaliseren we de veiligheid.