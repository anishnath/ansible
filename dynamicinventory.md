
```
ansible -i ec2.py -u ansible tag_tag_ansible  -m ping 

```
```
root@anish-ubuntu:/etc/ansible# export EC2_INI_PATH=/etc/ansible/ec2.ini
root@anish-ubuntu:/etc/ansible# export ANSIBLE_HOSTS=/etc/ansible/ec2.py
root@anish-ubuntu:/etc/ansible# ./ec2.py --list | grep i-0f969c8fca1f07482
        "ec2_id": "i-0f969c8fca1f07482", 
  "i-0f969c8fca1f07482": [
root@anish-ubuntu:/etc/ansible# ./ec2.py --list | grep i-0a848aa6ac0c6b247
        "ec2_id": "i-0a848aa6ac0c6b247", 
  "i-0a848aa6ac0c6b247": [
root@anish-ubuntu:/etc/ansible# 
root@anish-ubuntu:/etc/ansible# ansible -u ansible i-0a848aa6ac0c6b247  -m ping
34.201.250.101 | SUCCESS => {
    "changed": false, 
    "ping": "pong"
}
root@anish-ubuntu:/etc/ansible# ansible -u ansible i-0f969c8fca1f07482  -m ping
54.85.216.149 | SUCCESS => {
    "changed": false, 
    "ping": "pong"
}
root@anish-ubuntu:/etc/ansible# ansible -u ansible tag_ansible-redhat6  -m ping
 [WARNING]: No hosts matched, nothing to do

root@anish-ubuntu:/etc/ansible# ./ec2.py --list | grep ansible_redhat6
  "tag_Name_ansible_redhat6": [
root@anish-ubuntu:/etc/ansible# ansible -u ansible tag_Name_ansible_redhat6  -m ping
34.201.250.101 | SUCCESS => {
    "changed": false, 
    "ping": "pong"
}
root@anish-ubuntu:/etc/ansible# ansible -u ansible tag_Name_ansible*  -m ping
34.201.250.101 | SUCCESS => {
    "changed": false, 
    "ping": "pong"
}
54.85.216.149 | SUCCESS => {
    "changed": false, 
    "ping": "pong"
}

```
