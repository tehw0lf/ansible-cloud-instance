# provision a cloud instance running ubuntu minimal aarch64 with SSH, docker and unattended upgrades

create vars file
`echo "default_user: ubuntu" > vars.yml`
`echo "user: tehwolf" >> vars.yml`
`echo "instance_ip: ip_address" >> vars.yml`

create hosts file
`echo "[cloud_instance]" > hosts`
`echo "ubuntu ansible_ssh_host=ip_address ansible_user=tehwolf ansible_ssh_private_key_file=default_cloud_instance_ssh.key" >> hosts`

run ansible playbook
`ansible-playbook --inventory-file=hosts provision-cloud-instance.yml`
