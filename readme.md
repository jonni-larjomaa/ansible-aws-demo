Ansible aws example
---

## pre- requisites
    
    1. python 2.6 =>
    2. pip
    3. ansible
    4. boto
    
## setup
    
    1. pip install ansible
    2. pip install boto
    3. create credentials file called credentials.yml to include AWS keys
    
```yaml
    ---
    ec2_access_key: "--REMOVED--"
    ec2_secret_key: "--REMOVED--"
```
    
## dynamic inventory setup

http://docs.ansible.com/ansible/intro_dynamic_inventory.html#example-aws-ec2-external-inventory-script
    
## How to run

with static hosts file use:

`ansible-playbook -i hosts aws-playbook.yml`

With dynamic inventory use:

`ansible-playbook -i ec2.py aws-playbook.yml`

if you encrypted the credentials file with ansible vault use following line.

`ansible-playbook -i ec2.py aws-playbook.yml --ask-vault-pass`

if you want debug messages during runs add __-vvvv__
