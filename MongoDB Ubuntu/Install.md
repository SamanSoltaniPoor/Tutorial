### Install MongoDB on Ubuntu


<br>


#### 1 - Platform Support
22.04 LTS ("Jammy")\
20.04 LTS ("Focal")\
only supports the 64-bit versions
```sh
hostnamectl
```
Output :
```sh
Icon name        : computer-vm
Chassis          : vm
Machine ID       : 3fc6fd10f0fd96d900cedf724258e414
Boot ID          : 04b23146c31948539da67f06b3097320
Virtualization   : kvm
Operating System : Ubuntu 22.04.2 LTS   <---
Kernel           : Linux 5.15.0-70-generic
Architecture     : x86-64   <---
Hardware Vendor  : Red Hat
Hardware Model   : KVM
```


<br>


#### 2 - Import the public key used by the package management system
```sh
sudo apt-get install gnupg curl
```
```sh
curl -fsSL https://pgp.mongodb.com/server-7.0.asc | sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg --dearmor
```


<br>


#### 3 - Create a list file for MongoDB
```sh
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
```


<br>


#### 4 - Reload local package database
```sh
sudo apt-get update
```


<br>


#### 5 - Install MongoDB
```sh
sudo apt-get install -y mongodb-org
```


<br>


#### 6 - Start MongoDB
```sh
systemctl start mongod
```


<br>


#### 7 - Start automatically MongoDB after reboot
```sh
systemctl enable mongod
```


<br>


#### 8 - Check MongoDB
```sh
systemctl status mongod
```
Output :
```sh
● mongod.service - MongoDB Database Server
Loaded   : loaded (/lib/systemd/system/mongod.service; enabled; vendor preset: enabled)
Active   : active (running) since Wed 2023-10-04 17:40:19 UTC; 1min 36s ago   <---
Docs     : https://docs.mongodb.org/manual
Main PID : 3152 (mongod)
Memory   : 150.1M
CPU      : 2.326s
CGroup: /system.slice/mongod.service
└─3152 /usr/bin/mongod --config /etc/mongod.conf
```


<br>


#### 9 - Begin using MongoDB
To get started with MongoDB
```sh
mongosh
```
