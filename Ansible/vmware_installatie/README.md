Rolnaam
=========

Deze Ansible-rol installeert de vereiste dependencies voor het werken met VMware: `community.vmware`-collectie & `pyvmomi`-pakket

Vereisten
------------

- Ansible 2.10+
- Een werkende Python-interpreter

Variabelen
--------------

Geen

Dependencies
----------------

- `community.general` Ansible-collectie

Voorbeeld van een playbook
----------------

Hier is een voorbeeld van hoe deze rol gebruikt kan worden in een playbook:
```
- name: Installeer VMware dependencies
  hosts: all
  become: yes

  roles:
    - vmware_installation
```
Licentie
-------

MIT

Auteursinformatie
------------------

Deze rol is gemaakt door Samrat van Alpha males voor het VlaVirGem project.
