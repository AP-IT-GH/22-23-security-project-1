# Ansible Handleiding

Deze handleiding geeft een overzicht van de stappen die moeten worden genomen om het Ansible-gebeuren uit te voeren en specifiek het playbook deploy_vm.yml te gebruiken. Door het volgen van deze stappen kun je een geautomatiseerd implementatieproces creëren voor het implementeren van virtuele machines op ESXi-host(s). Door gebruik te maken van het hosts-bestand kun je de ESXi-host(s) specificeren en de vereiste inloggegevens configureren. De variabelen in de rol VM_OVA_deploy kunnen worden aangepast om de implementatie naar wens te configureren.

Zodra de benodigde configuraties zijn voltooid, kun je het deploy_vm.yml playbook uitvoeren met behulp van het commando: "ansible-playbook deploy_vm.yml". Hiermee wordt het implementatieproces gestart en worden de virtuele machines op de ESXi-hosts geïmplementeerd volgens de opgegeven configuraties nadat de variabelen zijn aangepast.

## Structuur van de Ansible-bestanden
De Ansible-bestanden moeten correct worden georganiseerd op je systeem. Hier is een voorbeeld van de directorystructuur:

ansible/
├── ansible.cfg
├── deploy_vm.yml
├── hosts
└── roles

## Ansible config bestand
Het bestand kan d.m.v. de template hieronder opgesteld worden:

[defaults]
inventory =./hosts
ansible_python_interpreter=/usr/bin/python3.9

## Hosts bestand
De ESXI host(s) kunnen d.m.v. de template hieronder geconfigureerd worden:

[ESXI]
esxi_host ansible_host="esxi-ipadres"

[ESXI:vars]
ansible_user="esxi gebruikersnaam"
ansible_password="esxi wachtwoord"
ansible_connection=local

# Variabelen meegeven
Dit wordt gedaan in de rol VM_OVA_deploy onder vars/main.yml:


ansible-playbook deploy_vm.yml
