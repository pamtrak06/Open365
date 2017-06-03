Open365 Installer
=================

# Overview

This is the main [Open365](https://open365.io/) installer. It installs all the required components to
run Open365 in your computer.

# Requirements

- Docker
- Docker-compose (1.3 or higher)
- Docker-machine (optional if docker engine higher then 1.9.1)
- Python3

### Python packages
- Debian / Ubuntu:

```
 $ apt-get install libmysqlclient-dev python3-dev
 $ pip3 install mysqlclient 
 $ pip3 install pymongo
 $ pip3 install ldap3
 $ pip3 install requests
```

- Fedora

```
 $ pip3 install pymongo
 $ pip3 install ldap3
 $ pip3 install requests
 $ yum install python3-mysql
```

We require SELinux to be disabled.

- Mac osx

```
 $ xcode-select --install
 $ brew tap brona/iproute2mac
 $ pip3 install pymongo
 $ pip3 install ldap3
 $ pip3 install requests
 $ yum install mysqlclient
```

Install docker-machine and execute following to get version 1.9.1 of docker engine :

```
docker-machine create node-open365 -d virtualbox     --virtualbox-boot2docker-url https://github.com/boot2docker/boot2docker/releases/download/v1.9.1/boot2docker.iso
docker-machine env node-open365
eval $(docker-machine env node-open365)
docker-machine ip node-open365
```

# How to use it

## Install Open365

Execute the next command and follow the instructions:

    $ sudo ./open365 install

This will download all the required docker images, and start running open365.
In this beta release these images can occupy more than 15gb of space. We are
in the process of reducing this to a respectable number.

## Uninstall Open365

If you want to uninstall Open365, you just need to run:

    $ sudo ./open365 destroy

This command will clean everything related with Open365.

## Create users and domain

If you want to create new users run the following command:

    $ sudo ./open365 user-create USERNAME --firstname FIRSTNAME --surname SURNAME --password PASS --email USER_EMAIL

For more information about this command run:

    $ sudo ./open365 user-create -h

Since it is possible to create users in different domains, there is an option to
create new domains:

    $ sudo ./open365 create-domain DOMAIN

# Contribute

[Contribute](CONTRIBUTING.md)

# Issue Tracking
We use the GitHub issue tracking.

# Licensing
Open365 is licensed under the AGPL. Check [LICENSE](LICENSE) for licensing information.
