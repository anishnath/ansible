# Ansible User Setup on Controller Node 
Create ansible remote user to manage the installation from Ansible Controller node. This user should have appropriate sudo privileges. An example sudoers entry is given below.

### Add user ansible
```
[root@controller-node]sudo adduser ansible
```
### Swicth to Ansible User
```
[root@controller-node]sudo su - ansible
```
### Generate the SSH-keyPair
```
[root@controller-node]ssh-keygen -t rsa -b 4096 -C "ansible"
```
### copy the id_rsa.pub file
```
[ansible@controller-node]cd /home/ansible/.ssh/
[ansible@controller-node .ssh]$ ls
id_rsa  id_rsa.pub
```

__Note down the public Key and copy it over in the Other machines__

```
[ansible@controller-node .ssh]$ cat id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAgEApeDUYGwaMfHd7/Zo0nzHA69uF/f99BYktwp82qA8+osph1LdJ/NpDIxcx3yMzWJHK0eg2yapHyeMpKuRlzxHHnmc99lO4tHrgpoSoyFF0ZGzDqgtj8IHS8/6bz4t5qcs0aphyBJK5qUYPhUqAL2Sojn+jLnLlLvLFwnv5CwSYeHYzLPHU7VWJgkoahyAlkdQm2XsFpa+ZpWEWTiSL5nrJh5aA3bgGHGJU2iVDxj2vfgPHQWQTiNrxbaSfZxdfYQx/VxIERZvc5vkfycBHVwanFD4vMn728ht8cE4VjVrGyTVznzrM7XC2iMsQkvmeYTIO2q2u/8x4dS/hBkBdVG/fjgqb78EpEUP11eKYM4JFCK7B0/zNaS56KFUPksZaSofokonFeGilr8wxLmpT2X1Ub9VwbZV/ppb2LoCkgG6RnDZCf7pUA+CjOYYV4RWXO6SaV12lSxrg7kvVYXHOMHQuAp8ZHjejh2/4Q4jNnweciuG3EkLOTiECBB0HgMSeKO4RMzFioMwavlyn5q7z4S82d/yRzsOS39qwkaEPRHTCg9F6pbZAAVCvGXP4nlyrqk26KG7S3Eoz3LZjcyt9xqGLzt2frvd+jLMpgvnlXTFgGA1ITExOHRb+FirmQZgnoiFbvpeIFj65d0vRIuY6VneIJ6EFcLGPpzeus0yLoDN1v8= ansible

[ansible@controller-node $ exit
[root@controller-node $ exit 
```
## Update the /etc/sudoers.d and add the ansible user
```
[root@controller-node $ visudo 
#includedir /etc/sudoers.d
ansible      ALL=(ALL)       NOPASSWD: ALL
```


# Ansible user setup on target Node 

Create a file named __authorized_keys__ in the .ssh directory and change its file permissions to 600 (only the owner can read or write to the file).

```
[root@nod1]sudo adduser ansible
[root@node1]sudo su - ansible
[ansible ~]$ cd /home/ansible
[ansible ~]$ mkdir .ssh
[ansible ~]$ touch authorized_keys
[ansible ~]$ chmod 600 authorized_keys
```
Copy the SSH public key from the __ansible_controller__ node and add it to all the VM which is 

```
[ansible ~]$ cat authorized_keys
ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAgEApeDUYGwaMfHd7/Zo0nzHA69uF/f99BYktwp82qA8+osph1LdJ/NpDIxcx3yMzWJHK0eg2yapHyeMpKuRlzxHHnmc99lO4tHrgpoSoyFF0ZGzDqgtj8IHS8/6bz4t5qcs0aphyBJK5qUYPhUqAL2Sojn+jLnLlLvLFwnv5CwSYeHYzLPHU7VWJgkoahyAlkdQm2XsFpa+ZpWEWTiSL5nrJh5aA3bgGHGJU2iVDxj2vfgPHQWQTiNrxbaSfZxdfYQx/VxIERZvc5vkfycBHVwanFD4vMn728ht8cE4VjVrGyTVznzrM7XC2iMsQkvmeYTIO2q2u/8x4dS/hBkBdVG/fjgqb78EpEUP11eKYM4JFCK7B0/zNaS56KFUPksZaSofokonFeGilr8wxLmpT2X1Ub9VwbZV/ppb2LoCkgG6RnDZCf7pUA+CjOYYV4RWXO6SaV12lSxrg7kvVYXHOMHQuAp8ZHjejh2/4Q4jNnweciuG3EkLOTiECBB0HgMSeKO4RMzFioMwavlyn5q7z4S82d/yRzsOS39qwkaEPRHTCg9F6pbZAAVCvGXP4nlyrqk26KG7S3Eoz3LZjcyt9xqGLzt2frvd+jLMpgvnlXTFgGA1ITExOHRb+FirmQZgnoiFbvpeIFj65d0vRIuY6VneIJ6EFcLGPpzeus0yLoDN1v8= ansible

```

From the Ansible Controller run the following command for each target node:
```
[ansible@controller-node] ssh-copy-id ansible@hostname
```
