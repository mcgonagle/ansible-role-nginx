# NGINX+ Ansbile Demo



### Requirements

* [Ansible 2.2.0 or greater][installing]


### Documentation
Pip does not come pre-installed on a mac. To install run 

```
sudo easy_install pip
sudo pip install --upgrade pip
```

Next, make sure virtualenv is installed.

```
pip install virtualenv
```

This will make available to you a virtualenv command. You can use that it make a virtual environment for your Ansible installation.

```
virtualenv ansible2
```

In your current working directory, you will find a new directory called ansible2. In this directory resides a copy of Python that is configured to install any modules inside of that local directory. Via this method, we can install Python modules without stomping on the system wide ones.

To use this new location, you must activate it.

```
. ansible2/bin/activate
```

You should see your prompt change so that the name of the virtualenv is prefixing the normal prompt. For example.

```
(ansible2) tom@tompro:~/Ansible/ansible-f5>
```

Now that our virtualenv is active, all future Python commands (such as pip) will install modules into the virtualenv. So let’s install the development copy of ansible.

```
pip install git+git://github.com/ansible/ansible.git@devel
```

You should be able to verify that you are running the new version of Ansible by using the –version argument to the ansible command, like so.

```
ansible --version
```

You should be presented with output that resembles the following

```
ansible --version
ansible 2.3.0
  config file =
  configured module search path = Default w/o overrides
```

## ansible-vault
```
sudo pip install ansible-vault
```

Create the ansible-vault file
```
ansible-vault create password.yml
```

Edit the ansible-vault file
```
ansible-vault edit password.yml
```
Contents of the ansible-vault file
```
    username: admin
    password: admin
```

Run the ansible-playbook command with the ansible-vault file 
```
ansible-playbook site.yml --ask-vault-pass -e @password.yml -vvv
```
ansible-vault password for file password.yml is ```password```


