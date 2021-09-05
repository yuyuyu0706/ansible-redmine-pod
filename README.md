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

## Inventory Test
```
ansible all -m ping -i ./inventory.yml
```

## Exec FirstBuild Ansible
[sample.log](https://github.com/yuyuyu0706/ansible-redmine-pod/blob/main/log/ansible-test.log)

```
ansible-playbook -i ./inventory.yml ./firstbuild.yml --syntax-check
ansible-playbook -i ./inventory.yml ./firstbuild.yml --check
ansible-playbook -i ./inventory.yml ./firstbuild.yml
```

## Exec Redmine Ansible
```
ansible-playbook -i ./inventory.yml ./redmine.yml --syntax-check
ansible-playbook -i ./inventory.yml ./redmine.yml --check
ansible-playbook -i ./inventory.yml ./redmine.yml

# Install redmine-plugins
ansible-playbook -i ./inventory.yml ./redmine-plugin.yml
```
