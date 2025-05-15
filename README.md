# provision a cloud instance running ubuntu minimal with SSH, docker and unattended upgrades

create vars file
`echo "arch: arm64" > vars.yml`
`echo "default_user: ubuntu" > vars.yml`
`echo "main_user: tehwolf" >> vars.yml`
`echo "users_to_remove:" >> vars.yml`
`echo "  - opc" >> vars.yml`
`echo "  - ubuntu" >> vars.yml`

create hosts file
`echo "[cloud_instance]" > hosts`
`echo "ubuntu ansible_ssh_host=ip_address" >> hosts`

create your instance with your SSH public key and add the key to your SSH agent

run ansible playbook
`ansible-playbook --inventory-file=hosts provision-cloud-instance.yml`
