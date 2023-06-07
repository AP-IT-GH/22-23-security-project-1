# Ansible Handleiding

Deze handleiding geeft een overzicht van de stappen die moeten worden genomen om het Ansible-gebeuren uit te voeren en specifiek het playbook `deploy_vm.yml` te gebruiken. Door het volgen van deze stappen kan je virtuele machines implementeren op een ESXi-host. Door gebruik te maken van het `hosts` bestand kan je de ESXi-host configureren met de vereiste inloggegevens. De variabelen in de rol `VM_OVA_deploy` kunnen worden aangepast om de implementatie naar wens te configureren. Door de playbook te starten, worden de virtuele machines op de ESXi-hosts geïmplementeerd volgens de opgegeven configuraties nadat de variabelen eerst zijn aangepast.

## Structuur van de Ansible-bestanden
De Ansible-bestanden moeten correct worden georganiseerd op het systeem. Hier is een voorbeeld van de directorystructuur:

### Inhoud map ansible:
* `ansible.cfg`
* `hosts`
* `roles` (met de rollen erin)
* `deploy_vm.yml`

## Ansible-configbestand
Het bestand kan d.m.v. de template hieronder opgesteld worden:
```
[defaults]
inventory =./hosts
ansible_python_interpreter=/usr/bin/python3.9
```
## Hostsbestand
De ESXI host(s) kunnen d.m.v. de template hieronder geconfigureerd worden:
```
[ESXI]
esxi_host ansible_host="<esxi ipadres>"

[ESXI:vars]
ansible_user="<esxi gebruikersnaam>"
ansible_password="<esxi wachtwoord>"
ansible_connection=local
```
## Rollen
Er worden twee rollen gebruikt: `VM_OVA_deploy` en `vmware_installatie`.

### 1) vmware_installatie
Installeert de vereiste dependencies voor het werken met VMware, namelijk de community.vmware collectie en het pyvmomi-pakket. Deze rol vereist geen specifieke variabelen, maar vereist wel Ansible 2.10+ en een werkende Python-interpreter met versie 3.9.

### 2) VM_OVA_deploy
Is verantwoordelijk voor het implementeren van een virtuele machine vanuit een OVA-bestand op een ESXi-host. Het maakt gebruik van de VMware modules van de community.vmware collectie om de implementatie uit te voeren. 

## Variabelen meegeven
Dit wordt gedaan in de rol VM_OVA_deploy onder vars/main.yml. De volgende variabelen zijn vereist:

* `portgroup_naam`: de naam van de portgroup voor het VM-netwerk.
* `vlan_id`: de VLAN-ID voor het VM-netwerk.
* `switch_naam`: de naam van de vSwitch.
* `datastore_naam`: de naam van de datastore waar de VM moet worden geplaatst.
* `ova_pad`: het lokale pad naar het OVA-bestand dat moet worden geïmplementeerd.
* `vm_naam`: de naam van de VM.
* `valideer_certificaten`: geeft aan of certificaten moeten worden gevalideerd bij het verbinden met de ESXi-host. Standaard staat dit op false.
* `host_naam`: een lijst van ESXi-hostnamen waarop de VM moet worden geïmplementeerd.

## Playbook uitvoeren
Zodra de hierboven genoemde configuraties zijn voltooid, kunt u het deploy_vm.yml playbook uitvoeren met behulp van het commando: `ansible-playbook deploy_vm.yml`.
***
