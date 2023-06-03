# VlaVirGem

In dit project wordt gebruik gemaakt van Ansible om een digitale tweeling van een Vlaamse gemeente te maken. De scripts zijn specifiek ontworpen voor gebruik op een VMWare ESXI-host. Deze omgeving kan dienen als testomgeving voor het implementeren van nieuwe programma's of als educatief hulpmiddel.

## Inhoud

### [Ansible](Ansible)
De hoofdmap van het Ansible gedeelte. Het bevat de rollen en playbook:

  - [VM_OVA_deploy](Ansible/VM_OVA_deploy): rol voor het implementeren van een virtuele machine vanuit een OVA-bestand. 

  - [VMWare_installatie](Ansible/vmware_installatie): rol voor het installeren van de vereiste dependencies voor het werken met VMware. 

  - [Deploy_VM.yml](Ansible/vmware_installatie): playbook voor het implementeren van de virtuele machine nadat de hosts en variabelen zijn geconfigureerd.

### [Data](Data)
Bevat dummygegevens die kunnen worden gebruikt in de gemeente-applicaties. Deze gegevens zijn willekeurig gegenereerd en simuleren de gegevens die je zou vinden in een gemeentelijke database over burgers. Dit zorgt ervoor dat je kunt testen zonder inbreuk te maken op de privacy.

### [Documentatie](Documentatie)
Bevat verschillende tekstbestanden met documentatie en informatie over het project. Hier vind je een aantal dagelijkse scrumbesprekingen. 

### [Webserver](Webserver)
Bevat de frontend van de webserver.

### [Extra_informatie](extra_informatie)
Bevat extra informatie met betrekking tot het project.
  - [Ansible-handleiding](extra_informatie/ansible.md)
  - [OVA- en ISO-bestanden](extra_informatie/ova.md)
  - [Netwerkopstelling](extra_informatie/netwerking.md)

### [Foto](foto)
Bevat afbeeldingen die relevant zijn voor het project, zoals netwerkschema's.

## Teamleden
- Adhekari Samrat
- Van Bosch Sasha
- Elâl-Lati Ilias
- De Feyter Bryan
