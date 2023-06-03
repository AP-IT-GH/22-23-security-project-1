# Deployen van VM networks en OVA's
## Networks aanmaken
1. Ga op de Bansible host
2. Ga naar root/ansible/scripts/esxi-deployer.yaml
3. Pas de nodige instellingen aan zoals de naam, vlan_id en switch. Zie hieronder.
---
- name: ESXI deploy VMs from OVA
  hosts: ESXI
  tasks:
    - name: Create VM network
      vmware_portgroup:
        hostname: "{{ ansible_host }}"
        username: "{{ ansible_user }}"
        password: "{{ ansible_password }}"
        validate_certs: no
        portgroup: "B_VLAN_test"
        vlan_id: 166
        switch: "VSWITCHB"
        hosts: "VLAVIRAB.p.bletchley.cloud"
      delegate_to: localhost
      
4. Voer de playbook uit met de volgende commando: ansible-playbook esxi-deployer.yaml

## OVA's aanmaken
1. Ga op de Bansible host
2. Ga naar root/ansible/scripts/esxi-deplyer.yaml
3. Pas de nodige instellingen aan zoals de naam van de VM, Switch waarmee je de VM wilt verbinden en switch. Zie hieronder.
---
- name: Deploy VM from OVA
      community.vmware.vmware_deploy_ovf:
        hostname: "{{ ansible_host }}"
        username: "{{ ansible_user }}"
        password: "{{ ansible_password }}"
        validate_certs: false
        name: "B_DSL"
        networks:
          VSWITCHB: "B_VLAN_test"
        datastore: "Datastore-secB"
        ovf: "/root/OVAs/DSL.ova"
        port: 80
        power_on: true
      delegate_to: localhost
      
4. Voer de playbook uit met de volgende commando: ansible-playbook esxi-deployer.yaml
