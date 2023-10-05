# Tutorial / MongoDB / Remote on Ubuntu


<br>


## Fast Step
Just run this code \
it's Done :100:
```sh
sudo apt-get install gnupg curl; curl -fsSL https://pgp.mongodb.com/server-7.0.asc | sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg --dearmor; echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list; sudo apt-get update; sudo apt-get install -y mongodb-org; systemctl start mongod; systemctl enable mongod; mongosh
```

<br>


## ( 01 step ) Platform Support
22.04 LTS ("Jammy")\
20.04 LTS ("Focal")\
only supports the 64-bit versions
```sh
hostnamectl
```
> ***Output :*** \
> \
> Icon name : computer-vm \
> Chassis : vm \
> Machine ID : 3fc6fd10f0fd96d900cedf724258e414 \
> Boot ID : 04b23146c31948539da67f06b3097320 \
> Virtualization : kvm \
> :green_circle: Operating System : Ubuntu 22.04.2 LTS \
> Kernel : Linux 5.15.0-70-generic \
> :green_circle: Architecture : x86-64 \
> Hardware Vendor : Red Hat \
> Hardware Model : KVM


<br>


## ( 02 step ) Import the public key used by the package management system
```sh
sudo apt-get install gnupg curl
```
```sh
curl -fsSL https://pgp.mongodb.com/server-7.0.asc | sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg --dearmor
```


<br>


## ( 03 step ) Create a list file for MongoDB
```sh
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
```


<br>


## ( 04 step ) Reload local package database
```sh
sudo apt-get update
```


<br>


## ( 05 step ) Install MongoDB
```sh
sudo apt-get install -y mongodb-org
```


<br>


## ( 06 step ) Start MongoDB
```sh
systemctl start mongod
```


<br>


## ( 07 step ) Start automatically MongoDB after reboot
```sh
systemctl enable mongod
```


<br>


## ( 08 step ) Check MongoDB
```sh
systemctl status mongod
```
> ***Output :*** \
> \
> ● mongod.service - MongoDB Database Server \
> Loaded : loaded (/lib/systemd/system/mongod.service; enabled; vendor preset: enabled) \
> :green_circle: Active : active (running) since Wed 2023-10-04 17:40:19 UTC; 1min 36s ago \
> Docs : httpss://docs.mongodb.org/manual \
> Main PID : 3152 (mongod) \
> Memory : 150.1M \
> CPU : 2.326s \
> CGroup: /system.slice/mongod.service \
> └─3152 /usr/bin/mongod --config /etc/mongod.conf


<br>


## ( 09 step ) Begin using MongoDB
To get started with MongoDB
```sh
mongosh
```
> ***Output :*** \
> \
> Current Mongosh Log ID : 651decd8ba0d52ac4d3aef43 \
> Connecting to : mongodb://127.0.0.1:27017/?directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+2.0.1 \
> :green_circle: Using MongoDB : 7.0.2 \
> :green_circle: Using Mongosh : 2.0.1 \
> ... \
> test>
