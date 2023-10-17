# User Management Ansible Role

this role is a customize user management for Vasl compony.

> Warning : if you run a playbook with out any tags playbook stop and did not work

## How Run Playbook

### add user and group or update password :

for add user and group  you should run playbook with tag << create_update_user >>
for example:

```bash
sudo ansible-playbook -i inventory/test-on-inventory playbook.yml --tags=create_update_user
```

### remove users and group:

for remove user group you should run playbook with tag << remove_group_user >>
for example:

```bash
ansible-playbook -i inventories/test-on-inventory -l 192.168.130.79,192.168.130.79,elk playbook_user_management.yml --tags=single_or_multi_delete_user -e "delete_user=aa,dev,data,srv" --ask-vault-pass
```

### change and update root password:

for change and update root user you should run playbook with this tag << change_root_password >>
for example:

```bash
sudo ansible-playbook -i inventory/test-on-inventory playbook.yml --tags=change_root_password
```

## Customize Users Variable
for change attribute users you can edit yaml file in vars directory
for example:

```bash
sudo vi roles/user_management/tasks/main.yml
```
take look at variable:
```yaml

```

username: << sample user name >>

password: << sample password >>

shell: << sample user shell path >>

groups: << sample user group to join it >>

> Warning : any user has group name with own user name so << groups >> variable is for add user to more groups exist on host.    
> if you don't have any groups don't use this parameter and remove it

ip: << sample list ip >>

> Warning : if you want run task in specific host you can create list of ip address  
> if you don't have any ip address list don't use this parameter and remove it

inv: << sample inventory group name>>

> Warning : this parameter is <u>required</u> if you want run task in specific inventory group name use this parameter  
> if you don't have any inventory group name use this parameter as null parameter

