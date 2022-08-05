# Container Template 

## Done ONCE at template creation
### Preparation

Execute in container ***as root***
```
apt update
apt upgrade -y


### install essentials
#tmux curl
apt install tmux curl -y
#kubectl
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
#install
install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

apt clean
apt autoremove

cd /etc/ssh
rm ssh_host_*
#do not disconnect from ssh hereinafter

truncate -s 0 /etc/machine-id

poweroff
```

### Convert to container template
Execute from Proxmox web UI

## For each instance created from template

### Create instance from template
Execute from Proxmox web UI

### Boot instance and configure (workaround for absence of cloudinit)
```
cd /etc/ssh
rm ssh_host_*
dpkg-reconfigure openssh-server #regen host keys
```
