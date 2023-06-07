# README.md

***Simply install jenkins:2.401.1 & blueocean***


## First build the custom docker image

```
docker build -t jenkins-blueocean:2.401.1 .
```

## Create jenkins data directory with permissions

```
mkdir /var/jenkins_home
```

## Allow read write & execute permissions to this directory.

```
chmod -R 777 /var/jenkins_home
```

## Run the docker container

```
docker-compose up -d
```
  


## About the installation:  

* __Image:__      jenkins-blueocean:2.401.1
* __Name:__       jenkins-blueocean  
* __Data:__       /var/jenkins_home  
* __Certs:__      /var/jenkins_home/certs/client:ro  

