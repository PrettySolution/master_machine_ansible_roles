# master_machine_ansible_roles
1. $ `apt update && apt install software-properties-common make -y && apt-add-repository --yes --update ppa:ansible/ansible && apt update && apt install ansible -y`
- installs ansible
1. $ `ansible-playbook install_docker_on_ubuntu.yml` 
- installs the latest docker, docker-composer on Ubuntu


