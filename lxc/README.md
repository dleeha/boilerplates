# Container Template 

## Done ONCE at template creation
### Preparation

Execute in container
```
sudo apt update
sudo apt upgrade -y
sudo apt clean
sudo apt autoremove

cd /etc/ssh
sudo rm ssh_host_*
#do not disconnect from ssh hereinafter

sudo truncate -s 0 /etc/machine-id

sudo poweroff
```

### Convert to container template
Execute from Proxmox web UI

## For each instance created from template

### Create instance from template
Execute from Proxmox web UI

### Boot instance and configure (workaround for absence of cloudinit)
```
cd /etc/ssh
sudo rm ssh_host_*
sudo dpkg-reconfigure openssh-server #regen host keys
```
