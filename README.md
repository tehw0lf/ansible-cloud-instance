# provision a cloud instance running ubuntu minimal with SSH, docker and unattended upgrades

create `vars.yml`:
```yml
arch: arm64
default_user: ubuntu
main_user: your_user
main_user_pass: your_password
users_to_remove:
  - opc
  - ubuntu
```
create hosts file
`echo "[cloud_instance]" > hosts`
`echo "ubuntu ansible_ssh_host=ip_address" >> hosts`

create your instance with your SSH public key and add the key to your SSH agent

run first ansible playbook
`ansible-playbook -i hosts provision-cloud-instance.yml`

run second ansible playbook to delete the default users
`ansible-playbook -i hosts remove-default-users.yml`
