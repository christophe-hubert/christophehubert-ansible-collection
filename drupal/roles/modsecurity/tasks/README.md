
Description
===========

This is an Ansible role 
that can install and uninstall 
ModSecurity+CRS on an Apache webserver.

It is the offical Ansible working repository of 
the ModSecurity team
and the OWASP Core Rule Set team.

If you have suggestions 
or constructive feedback,
please provide it here.

Dependencies
============

``` 
yum install python \ 
  git \
  python-pip \
  gcc \
  python-devel \
  libffi-devel \
  openssl-devel \
  yum-python
```

``` easy_install --upgrade pip && /usr/local/bin/pip install --upgrade pip ```

``` git clone https://github.com/csanders-git/ansible-role-modsecurity ```

*On Amazon Linux /usr/local/bin is not in the path so you should either add it using ```PATH=/usr/local/bin:$PATH``` or use the full path when calling ansible-playbook.*

This role requires Ansible 2.0 or higher and either a debian or redhat based OS. To install Ansible run the requirements.txt ```/usr/local/bin/pip2.7 install -r requirements.txt```

Examples
========

Install ModSec:
```/usr/local/bin/ansible-playbook modsecurity.yaml --tags "modsec_install"```

Install CRS:
```/usr/local/bin/ansible-playbook modsecurity.yaml --tags "crs_install"```

Note: By default this will install CRS master branch (v3). If you'd like a different version override the crs_version variable.
```/usr/local/bin/ansible-playbook modsecurity.yaml --tags "crs_install" --extra-vars "crs_version=v2.2/master"```

Uninstall CRS:
```/usr/local/bin/ansible-playbook modsecurity.yaml --tags "crs_uninstall"```

Uninstall ModSec:
```/usr/local/bin/ansible-playbook modsecurity.yaml --tags "modsec_uninstall"```

License
=======
License: Apache 2.0
Author: Chaim Sanders (@csanders-git) and contributors

