# Ansible Installation on Redhat/Centos 6 & 7

#### If you're on RedHat/CentOS 6:

```
bash ~#  rpm -ivh http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm
```
#### If you're on RedHat/CentOS 7 :   
```
bash ~#  rpm -ivh http://dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-5.noarch.rpm
```
## Pre-requistie Install python and pip

### Installing pip
To install pip, securely download [get-pip.py] (https://bootstrap.pypa.io/get-pip.py)

```
bash ~#  wget https://bootstrap.pypa.io/get-pip.py
```
Then run the following:

```
bash ~# python get-pip.py
```

Check the pip versionn 

```
bash ~#  pip -V
pip 9.0.1 from /usr/lib/python2.6/site-packages (python 2.6)
```
