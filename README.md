# Ansible Playbook for installing Tor Hidden Service V3

> This playbook has for purpose to install an hidden service on a VPS running Debian and using Apache HTTP Server

First step, prepare your environment :

```
python3 -m venv venv
. venv/bin/activate
pip install -U pip setuptools
pip install -r requirements.txt
```

At this step, Ansible should be installed into a Python Virtual Env.
You can launch the install playbook with

```
ansible-playbook playbooks/install_tor_hsv3.yml -i inventory --ask-vault-password
```

The playbook will: 

- Install TOR package using `apt`
- Configure a `.torrc` and generate a brand new Hidden Service V3 address
- Deploy a minimal website for testing purpose
- Install `apache2` and configure it to serve our Tor Hidden Service
- Test if it is accessible through TOR