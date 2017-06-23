# Ansible Installation on Ubuntu

Anisble Installtion can be Done in two ways 

1. PIP Based
2. Through apt-get repository

# PIP Based Installation
## Pre-requistie Install python and pip

Installing pip

To install pip, securely download [get-pip.py] (https://bootstrap.pypa.io/get-pip.py)

```
bash ~#  wget https://bootstrap.pypa.io/get-pip.py
```

Then run the following:
```
bash ~# python get-pip.py
```
Check the pip version
```
bash ~#  pip -V
pip 9.0.1 from /usr/lib/python2.6/site-packages (python 2.6)
```
## Install Common Dependencies

```
sudo apt-get install build-essential autoconf libtool pkg-config python-opengl python-imaging python-pyrex python-pyside.qtopengl idle-python2.7 qt4-dev-tools qt4-designer libqtgui4 libqtcore4 libqt4-xml libqt4-test libqt4-script libqt4-network libqt4-dbus python-qt4 python-qt4-gl libgle3 python-dev libssl-dev

```
## Install Ansible through PIP Version=2.2.1.0

```
bash ~:/home/ubuntu# pip install ansible==2.2.1.0
Collecting ansible==2.2.1.0
Requirement already satisfied: PyYAML in /usr/local/lib/python2.7/dist-packages (from ansible==2.2.1.0)
Collecting paramiko (from ansible==2.2.1.0)
  Using cached paramiko-2.2.1-py2.py3-none-any.whl
Requirement already satisfied: setuptools in /usr/local/lib/python2.7/dist-packages (from ansible==2.2.1.0)
Collecting jinja2<2.9 (from ansible==2.2.1.0)
  Using cached Jinja2-2.8.1-py2.py3-none-any.whl
Collecting pycrypto>=2.6 (from ansible==2.2.1.0)
Requirement already satisfied: pynacl>=1.0.1 in /usr/local/lib/python2.7/dist-packages (from paramiko->ansible==2.2.1.0)
Requirement already satisfied: pyasn1>=0.1.7 in /usr/local/lib/python2.7/dist-packages (from paramiko->ansible==2.2.1.0)
Requirement already satisfied: bcrypt>=3.1.3 in /usr/local/lib/python2.7/dist-packages (from paramiko->ansible==2.2.1.0)
Collecting cryptography>=1.1 (from paramiko->ansible==2.2.1.0)
  Using cached cryptography-1.9.tar.gz
Collecting MarkupSafe (from jinja2<2.9->ansible==2.2.1.0)
Requirement already satisfied: six in /usr/local/lib/python2.7/dist-packages (from pynacl>=1.0.1->paramiko->ansible==2.2.1.0)
Requirement already satisfied: cffi>=1.4.1 in /usr/local/lib/python2.7/dist-packages (from pynacl>=1.0.1->paramiko->ansible==2.2.1.0)
Requirement already satisfied: idna>=2.1 in /usr/local/lib/python2.7/dist-packages (from cryptography>=1.1->paramiko->ansible==2.2.1.0)
Requirement already satisfied: asn1crypto>=0.21.0 in /usr/local/lib/python2.7/dist-packages (from cryptography>=1.1->paramiko->ansible==2.2.1.0)
Requirement already satisfied: enum34 in /usr/local/lib/python2.7/dist-packages (from cryptography>=1.1->paramiko->ansible==2.2.1.0)
Requirement already satisfied: ipaddress in /usr/local/lib/python2.7/dist-packages (from cryptography>=1.1->paramiko->ansible==2.2.1.0)
Requirement already satisfied: pycparser in /usr/local/lib/python2.7/dist-packages (from cffi>=1.4.1->pynacl>=1.0.1->paramiko->ansible==2.2.1.0)
Building wheels for collected packages: cryptography
  Running setup.py bdist_wheel for cryptography ... done
  Stored in directory: /root/.cache/pip/wheels/ff/a5/ef/186bb4f6a89ef0bb8373bf53e5c9884b96722f0857bd3111b8
Successfully built cryptography
Installing collected packages: cryptography, paramiko, MarkupSafe, jinja2, pycrypto, ansible
Successfully installed MarkupSafe-1.0 ansible-2.2.1.0 cryptography-1.9 jinja2-2.8.1 paramiko-2.2.1 pycrypto-2.6.1

```
## Verify Ansible Installation

```
bash ~# ansible --version
ansible 2.2.1.0
  config file = 
  configured module search path = Default w/o overrides
  
```

## Alternate Installation through apt-get repository

Alternatively the same thing can be Installed using the `ppa:ansible/ansible` 

```
sudo apt-add-repository -y ppa:ansible/ansible
bash ~# sudo apt-get update
bash ~# sudo apt-get install -y ansible
```
