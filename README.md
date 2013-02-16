bfgminer ansible playbook
=========================

Deploy [bfgminer](http://github.com/luke-jr/bfgminer) with [ansible](http://ansible.cc).

Tested on [Fedora 18](http://fedoraproject.org) with [Butterfly Labs](http://butterflylabs.com) FPGA miners.

Features
--------

- Pulls in all dependencies and builds the latest code from git
- Installs configuration to /etc/bfgminer.conf
- Changes ownership of /dev/ttyUSB*
- Runs bfgminer with [systemd](http://www.freedesktop.org/wiki/Software/systemd) as the bfgminer user
- Ships logs to syslog

Installation
------------

```bash
sudo yum -y install ansible git
sudo systemctl start sshd
git clone git://github.com/lmacken/bfgminer-ansible
cd bfgminer-ansible
ansible-playbook --inventory 'localhost,' --ask-pass --ask-sudo-pass playbook.yml
```

