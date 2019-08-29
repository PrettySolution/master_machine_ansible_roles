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

