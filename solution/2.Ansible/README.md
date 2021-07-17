
# Install Ansible on control station
```
sudo apt-get install ansible -y
```

# Make hosts SSH accessible
```
ssh-keygen
ssh-copy-id node1 && ssh-copy-id node2 && ssh-copy-id node3
```


### Test ansible
```
ansible nodes -i myhosts -m command -a hostname
```

### Install Python 
```
ansible nodes -i myhosts -m command -a 'sudo apt-get -y install python-simplejson'
```

### Run the playbook to install docker
```
ansible-playbook -i myhosts -K playbook1.yml
```



