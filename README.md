# README.md

***Simply install jenkins:2.401.1 & blueocean***


## First build the custom docker image

```
docker build -t jenkins-blueocean:2.401.1-1 .
```

## Run the docker container

```
docker-compose up -d
```
  


## About the installation:  

* __Image:__      jenkins-blueocean:2.401.1-1  
* __Name:__       jenkins-blueocean  
* __Data:__       /var/jenkins_home  
* __Certs:__      /var/jenkins_home/certs/client:ro  

