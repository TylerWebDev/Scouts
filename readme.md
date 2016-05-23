# Boy Scouts Programming Badge Program

## Ensure dns is setup for:
> scout1.tylerwebdev.io
> scout2.tylerwebdev.io
> ...

## Setup server

> install ansible on control machine
> devel for yum_repository support
```
brew install --devel ansible
```

> clone this repository to the control machine
```
git clone git@github.com:TylerWebDev/Scouts.git
```

> install ansible dependencies
```
ansible-galaxy install -r requirements.yml
```

> run the playbook for the server listed in inventory.yml
```
ansible-playbook deploy.yml
```

## Misc (This is automated, but here for record)
> generate user password hash ("scouts" is the password for all scouts)
```
openssl passwd -1 "scouts"
```

> ensure virtual host mappings are setup in tomcat
```
/opt/lucee/tomcat/conf/server.xml
```

> Need the following entries
```xml
<Host name="scout1.tylerwebdev.io" appBase="/home/scout1"><Context path="" docBase=""/></Host>
<Host name="scout2.tylerwebdev.io" appBase="/home/scout2"><Context path="" docBase=""/></Host>
```

> and so on and so on

## Scout sites (Needs dns A records for each scout to point to server IP)
```
http://scout1.tylerwebdev.io/index.cfm
http://scout2.tylerwebdev.io/index.php
```

## Student editing
> https://codeanywhere.co
> connect sftp:// u: scout1 p: scouts
