## Ansible

Host file:
[ESXI]
esxi_host ansible_host=<ip-esxi>

[ESXI:vars]
ansible_user=<gebruikersnaam esxi>
ansible_password=<wachtwoord esxi>
ansible_connection=local
