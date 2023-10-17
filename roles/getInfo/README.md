# GetInfo Ansible Role

this role collect data with gathering facts module for Vasl compony

> Warning : if you run a playbook with out any tags playbook stop and did not work

## How Run Playbook

### Collect data nad send to mattermost
if you want send data to mattermost follow below: 

```shell
ansible-playbook -i inventories/asiatech  playbook_getInfo.yml  --ask-vault-pass -t getinfo_send_mattermost -e "matter_channel=@h.aynedar"
```
#### --extra-vars
matter_channel=<< put_here_mattermost_chanel_id >>