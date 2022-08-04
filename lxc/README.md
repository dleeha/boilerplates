## Container Template 

### Preparation

Execute in container
```
sudo apt update && sudo apt dist-upgrade -y

sudo apt clean
sudo apt autoremove

cd /etc/ssh
sudo rm ssh_host_*
#do not disconnect from ssh hereinafter

sudo truncate -s 0 /etc/machine-id

sudo poweroff
```

### Convert to container template

### Create instance from template

### Boot instance and configure (workaround for absence of cloudinit)
```
cd /etc/ssh
sudo rm ssh_host_*
sudo dpkg-reconfigure openssh-server #regen host keys
```
