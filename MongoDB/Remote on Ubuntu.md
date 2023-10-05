# Tutorial / MongoDB / Remote on Ubuntu


<br>


## ( 01 step ) Adjusting the Firewall
27017 port for MongoDB
```sh
sudo ufw enable
```
87.193.128.41 is your PC IP
```sh
sudo ufw allow from 87.193.128.41 to any port 27017
```
```sh
sudo ufw status
```


<br>


## ( 02 step ) Configuring a Public bindIP
```sh
sudo nano /etc/mongod.conf
```
24.95.162.31 is your VPS IP
```sh
net:
  port: 27017
  bindIp: 127.0.0.1,24.95.162.31
```
```sh
net:
sudo systemctl restart mongod
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
