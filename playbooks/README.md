# Pritnul VPN server with Ansible GCP

## How-To

```sh
sudo apt-get install python3-pip
sudo pip3 install virtualenv 
virtualenv .venv

git clone https://github.com/aguscuk/pritunl-ansible.git
cd pritunl-ansible

source ~/.venv/bin/activate
pip3 install -r requirements.txt

# checking inventories
ansible-inventory -i inventories/dev/ --graph
cd playbooks/

# dry-run
ANSIBLE_CONFIG=../ansible.cfg ansible-playbook pritun_playbookl.yml -i ../inventories/dev/ --extra-vars ansible_user=$USER -C

# run
ANSIBLE_CONFIG=../ansible.cfg ansible-playbook pritun_playbookl.yml -i ../inventories/dev/ --extra-vars ansible_user=$USER
```