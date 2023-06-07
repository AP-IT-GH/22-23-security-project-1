Rolnaam
=========

Deze Ansible-rol implementeert een VM vanuit een OVA-bestand op een ESXi-host.

Vereisten
------------

Toegang tot een ESXI-host
Een machine waarop ansible op draait
OVA-bestanden die lokaal staan

Variabelen
--------------

De volgende variabelen kunnen worden geconfigureerd voor deze rol:

- `portgroup_naam`: Naam van het portgroup voor het VM-netwerk
- `vlan_id`: VLAN-ID voor het VM-netwerk
- `switch_naam`: Naam van de vSwitch
- `datastore_naam`: Naam van de datastore waar de VM moet worden geplaatst
- `ova_pad`: Lokale pad naar het OVA-bestand dat moet worden geïmplementeerd
- `vm_naam`: Naam van de VM
- `valideer_certificaten`: Geeft aan of certificaten moeten worden gevalideerd bij het verbinden met de ESXi-host. Standaard staat dit op waarde 'false'.
- `host_naam`: Lijst van ESXi-hostnamen waarop de VM moet worden geïmplementeerd

Voorbeeld van een playbook
----------------

Hier is een voorbeeld van hoe deze rol gebruikt kan worden in een playbook:
```
- name: VM vanuit OVA implementeren achter een poortgroep
  hosts: ESXI

  roles:
    - VM_OVA_deploy
```

Licentie
-------

MIT

Auteursinformatie
------------------

Deze rol is gemaakt door Samrat van Alpha males voor het VlaVirGem project.
