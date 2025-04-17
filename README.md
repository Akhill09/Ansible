

To use vault and encrypted password create a file For example, a file password.yml with the following content can be created:

vcenter_password: "password"
This file can be encrypted with the following ansible-vault command:

ansible-vault encrypt password.yml


ansible-playbook vm_create_vault.yml --ask-vault-pass
