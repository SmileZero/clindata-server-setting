### 1. Install Ansible
MacOS: ```brew install ansible```


### 2. Put Server IP or DNS you want to set up in ./hosts
Create the ```./hosts``` and add server ip or dns to it.
You can find an example in ```./host.example```.
You can also put multiple server ip or DNS in the ```./host``` file line by line.


### 3. Exeute the command with your private key
```ansible-playbook -i ./hosts playbook/docker.yml -u ubuntu --private-key=<...>/msj.pem```


### 4. (Opational) Disable ```ssh``` key check
Setting up new servers will trigger ssh key checking as bellow:
```
GATHERING FACTS ***************************************************************
The authenticity of host 'xxx.xxx.xxx.xxx (xxx.xxx.xxx.xxx)' can't be established.
RSA key fingerprint is xx:yy:zz:....
Are you sure you want to continue connecting (yes/no)?
```

It may cause the command failed if you have multiple server to set up.
You can make ```~/.ansible.cfg```, and include this:
```
[defaults]
host_key_checking = False
```
