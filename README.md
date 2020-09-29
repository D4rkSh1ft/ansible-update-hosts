# Update Hosts

## Site-Wide APT Updates on Linux Hosts

## Environment Files
Remote passwords are not included in the playbook but are in the individual host and group vault files.

### Vault Files
These playbooks take advantage of vault files to store sensitive information.  Example vault files are included but are not encrypted.

#### Encrypt Vault Files
```bash
$ ansible-vault encrypt group_vars/proxmox/vault.yaml
```

### Vault Password
You have two options to decrypt vaults at runtime.
- Create a vault password file
- Run playbook with `--ask-vault-password`

#### Vault Password File
Create a file called `.vault_password_file` in the playbook directory that contains same password used to encrypt your vault files.  *Protect it the same as you would a password.*

#### Run Ansible-Playbook and ask for vault password
```bash
$ ansible-playbook --ask-vault-password update-hosts.yml
```

## Example Usage
```bash
$ ansible-playbook update-hosts.yml
```