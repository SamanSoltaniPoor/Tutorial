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
sudo systemctl restart mongod
```


<br>


## ( 03 step ) Testing Remote Connectivity
```sh

```




