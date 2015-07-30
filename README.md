###Ansible Playbooks    
Currently just one to setup an nginx reverse proxy. Run the ansible-playbook command on this after setting up hosts, it will ask for the reverse proxy.     

```
[user@server ansible]$ ansible-playbook main.yml -i /home/user/.ansible/hosts --private-key /home/user/.ssh/id_rsa -u root
Where is the proxy going? [someserver]: http://yoursite.tld

PLAY [make the nginx proxy] *************************************************** 

GATHERING FACTS *************************************************************** 
ok: [yoursite.tld]

TASK: [nginx | Ensure up to date] ********************************************* 
ok: [yoursite.tld]

TASK: [nginx | Enabled Epel] ************************************************** 
ok: [yoursite.tld]

TASK: [nginx | Add nginx] ***************************************************** 
ok: [yoursite.tld]

TASK: [nginx | open port] ***************************************************** 
changed: [yoursite.tld]

TASK: [nginx | copy template] ************************************************* 
ok: [yoursite.tld]

TASK: [nginx | enable nginx] ************************************************** 
ok: [yoursite.tld]

NOTIFIED: [nginx | restart firewall] ****************************************** 
changed: [yoursite.tld]

PLAY RECAP ******************************************************************** 
yoursite.tld        : ok=8    changed=2    unreachable=0    failed=0   

```
