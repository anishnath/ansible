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

# Install Ansible Packges package with specfic Versions

```
bash ~# sudo pip install pip –upgrade
bash ~# sudo pip install ansible==2.2.1.0
```

__Output__
```
bash ~#  sudo pip install ansible==2.2.1.0
DEPRECATION: Python 2.6 is no longer supported by the Python core team, please upgrade your Python. A future version of pip will drop support for Python 2.6
Collecting ansible==2.2.1.0
/usr/lib/python2.6/site-packages/pip/_vendor/requests/packages/urllib3/util/ssl_.py:318: SNIMissingWarning: An HTTPS request has been made, but the SNI (Subject Name Indication) extension to TLS is not available on this platform. This may cause the server to present an incorrect TLS certificate, which can cause validation failures. You can upgrade to a newer version of Python to solve this. For more information, see https://urllib3.readthedocs.io/en/latest/security.html#snimissingwarning.
  SNIMissingWarning
/usr/lib/python2.6/site-packages/pip/_vendor/requests/packages/urllib3/util/ssl_.py:122: InsecurePlatformWarning: A true SSLContext object is not available. This prevents urllib3 from configuring SSL appropriately and may cause certain SSL connections to fail. You can upgrade to a newer version of Python to solve this. For more information, see https://urllib3.readthedocs.io/en/latest/security.html#insecureplatformwarning.
  InsecurePlatformWarning
  Using cached ansible-2.2.1.0.tar.gz
/usr/lib/python2.6/site-packages/setuptools/command/install_scripts.py:3: UserWarning: Module backports was already imported from /usr/lib64/python2.6/site-packages/backports/__init__.pyc, but /usr/lib/python2.6/site-packages is being added to sys.path
  from pkg_resources import Distribution, PathMetadata, ensure_directory
Requirement already satisfied: paramiko in /usr/lib/python2.6/site-packages (from ansible==2.2.1.0)
Requirement already satisfied: jinja2<2.9 in /usr/lib64/python2.6/site-packages (from ansible==2.2.1.0)
Requirement already satisfied: PyYAML in /usr/lib64/python2.6/site-packages (from ansible==2.2.1.0)
Requirement already satisfied: setuptools in /usr/lib/python2.6/site-packages (from ansible==2.2.1.0)
Collecting pycrypto>=2.6 (from ansible==2.2.1.0)
  Using cached pycrypto-2.6.1.tar.gz
Requirement already satisfied: MarkupSafe in /usr/lib/python2.6/site-packages (from jinja2<2.9->ansible==2.2.1.0)
Building wheels for collected packages: ansible, pycrypto
  Running setup.py bdist_wheel for ansible ... error
  Complete output from command /usr/bin/python -u -c "import setuptools, tokenize;__file__='/tmp/pip-build-YOiswP/ansible/setup.py';f=getattr(tokenize, 'open', open)(__file__);code=f.read().replace('\r\n', '\n');f.close();exec(compile(code, __file__, 'exec'))" bdist_wheel -d /tmp/tmpyY0u2Xpip-wheel- --python-tag cp26:
  usage: -c [global_opts] cmd1 [cmd1_opts] [cmd2 [cmd2_opts] ...]
     or: -c --help [cmd1 cmd2 ...]
     or: -c --help-commands
     or: -c cmd --help
  
  error: invalid command 'bdist_wheel'
  
  ----------------------------------------
  Failed building wheel for ansible
  Running setup.py clean for ansible
  Running setup.py bdist_wheel for pycrypto ... error
  Complete output from command /usr/bin/python -u -c "import setuptools, tokenize;__file__='/tmp/pip-build-YOiswP/pycrypto/setup.py';f=getattr(tokenize, 'open', open)(__file__);code=f.read().replace('\r\n', '\n');f.close();exec(compile(code, __file__, 'exec'))" bdist_wheel -d /tmp/tmpkYQ1ZGpip-wheel- --python-tag cp26:
  usage: -c [global_opts] cmd1 [cmd1_opts] [cmd2 [cmd2_opts] ...]
     or: -c --help [cmd1 cmd2 ...]
     or: -c --help-commands
     or: -c cmd --help
  
  error: invalid command 'bdist_wheel'
  
  ----------------------------------------
  Failed building wheel for pycrypto
  Running setup.py clean for pycrypto
Failed to build ansible pycrypto
Installing collected packages: pycrypto, ansible
  Found existing installation: pycrypto 2.0.1
    DEPRECATION: Uninstalling a distutils installed project (pycrypto) has been deprecated and will be removed in a future version. This is due to the fact that uninstalling a distutils project will only partially uninstall the project.
    Uninstalling pycrypto-2.0.1:
      Successfully uninstalled pycrypto-2.0.1
  Running setup.py install for pycrypto ... done
  Running setup.py install for ansible ... done
Successfully installed ansible-2.2.1.0 pycrypto-2.6.1
```
# Verify the Ansible version 

```
bash ~#  ansible --version
ansible 2.2.1.0
  config file = 
  configured module search path = Default w/o overrides
bash ~#  
```
