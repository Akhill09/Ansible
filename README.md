

To use vault and encrypted password create a file For example, a file password.yml with the following content can be created:

vcenter_password: "password"
This file can be encrypted with the following ansible-vault command:

ansible-vault encrypt password.yml


ansible-playbook vm_create_vault.yml --ask-vault-pass


ansible-playbook vm_create.yml
vcenter_password: "password"
This file can be encrypted with the following ansible-vault command:

ansible-vault encrypt password.yml

ansible-playbook vm_create_vault.yml --ask-vault-pass

We need to create multiple VMS that have similar hardware requirements, the same OS, but some parameters such as vm_name, IP address, or disk size are different. The ansible iterating mechanism can be used with the syntax: with_items, where the dictionary variable “vms” is used. In this case, variables are referenced with item.variable_name. Also, vars_multiple.yml file will be customised accordingly.

vars_multiple.yml file will contain list of VMs that will be created and parameters with specific values, which are different for each VM. For example, parameters that are specific for each VM are vm_name, vm_ip and vm_disk_gb, other parameters are the same for all VMs, but can be adjusted.
