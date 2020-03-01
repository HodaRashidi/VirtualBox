# Virtual Box and Extension Pack Installation Guide

This document explains how to install VirtualBox 6 and Extension Pack.

## Installing VirtualBox 6

* Step 1: Update your system

The first step is to ensure your system is updated.

```bash
sudo apt update && apt -y upgrade
```

* Step 2: Import VirtualBox apt repository

Once the system is updated, import repository GPG key used for signing
packages.

```bash
sudo apt -y install wget
wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -
```

* Step 3: Add the VirtualBox Repository

After the importation of GPG key, add VirtualBox repository to your system
using the following commands.

```bash
echo "deb [arch=amd64] http://download.virtualbox.org/virtualbox/debian bionic contrib" | sudo tee /etc/apt/sources.list.d/virtualbox.list
```

* Step 4: Installing VirtualBox

The final step is the actual installation of VirtualBox and extension pack
which extends VirtualBox features.

```bash
sudo apt update
sudo apt install linux-headers-$(uname -r) dkms
sudo apt install virtualbox-6.0
```

## Installing Extension Pack

* Step 1: Download Extension Pack:

```bash
cd ~/
wget https://download.virtualbox.org/virtualbox/6.0.0/Oracle_VM_VirtualBox_Extension_Pack-6.0.0.vbox-extpack
```

You can also download it manually:
[VirtualBox](https://www.virtualbox.org/wiki/Downloads)

* Step 2: Extension Pack Installation

This command installs a new extension pack on the system.

```bash
vboxmanage extpack install <tarball>
```

`<tarball>` The file containing the extension pack to installed.

For more information, you can see [VBoxManage
extpack](https://www.virtualbox.org/manual/ch08.html#vboxmanage-extpack)
