# Ansible-Boilerplate

## Use this repository

Checkout as your Project and customize to your needs.
```bash
git clone https://github.com/tmflgr/ansible-boilerplate.git MyAnsibleProject
```

## Using Ansible

Install `ansible` on your device. i recommend using a package manager like `brew`. e.g. `brew install ansible`.

### Some useful commands

```bash
# ping host or group
ansible ${groupname|servername} -m ping -u root

# run a single command on a host or group
ansible ${groupname|servername} -m command -a "cat /etc/hosts/" -u root
```

### Vault Commands

all of those commands will open a vi!
if you want to change this prepend `EDITOR=nano`
```bash

# create a vault file
ansible-vault create group_vars/all/vault
# edit the vault file
ansible-vault edit group_vars/all/vault
# view the encrypted file
ansible-vault view group_vars/all/vault

```

### Run Playbooks
```bash
# run all tasks on specific inventory
ansible-playbook site.yml -i inventory.yml -v
    # Note that -v produces verbose output. -vv, -vvv and -vvvv  
    # are also available for even more (debug) output.
    
    (if you using a vault, append)
    --vault-password-file /path/to/pwfile
    or
    --ask-vault-pass

```
