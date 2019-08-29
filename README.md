# master_machine_CentOS7
ansible master machine
### to do on a master host (CentOS7 in my case using ESXi)
1. $ `nmtui` - to activate `ens192`
1. $ `ip a` - to look what's IP address 
1. $ `sed -i "s/BOOTPROTO=dhcp/BOOTPROTO=static/" /etc/sysconfig/network-scripts/ifcfg-ens192`
1. $ `sed -i "s/ONBOOT=no/ONBOOT=yes/" /etc/sysconfig/network-scripts/ifcfg-ens192`
1. $ 
```shell script
   echo "        IPADDR=192.168.15.20
        NETMASK=255.255.255.0
        GATEWAY=192.168.15.1
        DNS1=8.8.8.8" >> /etc/sysconfig/network-scripts/ifcfg-ens192
```
1. $ `hostnamectl set-hostname master`
1. $ `yum install epel-release -y` (EPEL repo stands for Extra Packages for Enterprise Linux Repository)
1. $ `yum install ansible git nano tree -y`
1. $ `mv /etc/ansible/ansible.cfg /etc/ansible/ansible.cfg.ORIG`
1. $ `ssh-keygen`
1. $ `ssh-copy-id localhost`
1. $ `cat /root/.ssh/id_rsa.pub`
1. Copy-paste your key to github
1. $ `git clone git@github.com:vasilgerman/master_machine_CentOS7.git`
1. $ `cd master_machine_CentOS7`
1. $ `ansible -m ping localhost` or `ansible-playbook ping-pong.yml` to check up 
1. $ `ansible-playbook localhost_install_docker_on_CentOS7.yml`