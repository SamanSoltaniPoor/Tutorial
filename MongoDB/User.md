# Tutorial / MongoDB / User
MongoDB does not require a username or password to access or modify the database


<br>


## ( 01 step ) Create admin user for all customer user
4444 is your password
```sh
use admin
```
```sh
db.createUser({user:'siteUserAdmin', pwd: '55555', roles:['userAdminAnyDatabase']})
```
```sh
db.auth('siteUserAdmin', '4444')
```


<br>


## ( 02 step ) Create customer user
saman is your username
55555 is your password
authgram is your database
```sh
db.createUser({user:'saman', pwd: '55555', roles:[{db:'authgram', role:'readWrite'}]})
```

<br>


## ( 03 step ) Testing Remote Connectivity
```sh

```
