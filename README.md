# ansible-redmine-pod

```
git clone https://github.com/yuyuyu0706/ansible-redmine-pod.git
```

## Sample inventory.yml
vi ./inventory.yml

```
its_server:
  hosts: ds9its11
  vars:
    ansible_user: vagrant
    ansible_password: vagrant
    ansible_ssh_private_key_file: ~/.ssh/xxxxxx
```

## Exec Test Ansible
[sample.log](https://github.com/yuyuyu0706/ansible-redmine-pod/blob/main/log/ansible-test.log)

```
ansible all -m ping -i ./inventory.yml
ansible-playbook -i ./inventory.yml ./redmine.yml --syntax-check
ansible-playbook -i ./inventory.yml ./redmine.yml --list-task
ansible-playbook -i ./inventory.yml ./redmine.yml --check  # DryRun
```

## Exec Ansible
```
# Install podman & git
ansible-playbook -i ./inventory.yml ./firstbuild.yml

# Install redmine
ansible-playbook -i ./inventory.yml ./redmine.yml

# Install redmine-plugins
ansible-playbook -i ./inventory.yml ./redmine-plugin.yml
```
