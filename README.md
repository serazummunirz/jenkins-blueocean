# jenkins

***Simply install jenkins:2.426.2-jdk17 & blueocean.***

## About:
This repository is made for RedSquirrel LLC.


## What is this repo about?

This repository contans necessary resources and instructions to configure a jenkins master agent with "jenkins_blueocean:2.426.2-jdk17" inside a docker container.

## Benifits:

* If you use the build method. Then it will be a fresh jenkins installation with blueocean plugin.
* If you are using the pull method then you will have a jenkins installation out of the box that has already installed with suggested plugin.
* Pull method is guaranteed to work forever for any application that needs to build docker image, delivers images to AWS ECR.


## Prerequisites:
* Any linux server that has docker installed.
* Open port TCP/8080, TCP/50000 from the firewall.
* AWS Cli installed following the AWS Instructions: https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html


### You should only follow below instructions if you are using the pull method.

* Create an "Access key" from AWS control panel for your user.
* Create 2 environment variables with below commands.

        export AWS_ACCESS_KEY_ID=your_access_key_id
        export AWS_SECRET_ACCESS_KEY=your_secret_access_key

* Login to the ECR private registry.

        aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 845151757650.dkr.ecr.us-east-1.amazonaws.com


## Methods:
There are 2 methods for configuring the agents "build" and "pull".

* build: If you want to build the image from scratch then you can follow this method. (Not necessary)
* pull: You can simply follow the pull method steps to pull the image from the AWS ECR and boot up the jenkins container. (Recommended.)


## Build:
If you choose to follow the build method you can follow below steps:

* Clone this git repository inside the linux system where you will run the jenkins master.
* Navigate to the build directory inside the git directory. "cd jenkins-docker/build"
* Create a directory to use as a persitant volume for jenkins and provide it full permission using bellow commands.

        mkdir /var/jenkins_home
        chmod -R 777 /var/jenkins_home


* Run this command to build the images: "docker-compose up -d"

Jenkins will be installed and run shortly inside a docker container.
It will be accessable in web via port 8080


## Pull:
If you choose to follow the pull method, feel free to follow below steps:

* Clone this git repository inside the linux system.
* Navigate to the build directory inside the git directory. "cd jenkins-docker/pull"
* Create a directory to use as a persitant volume for jenkins and provide it full permission using bellow commands.

        mkdir /var/jenkins_home
        chmod -R 777 /var/jenkins_home

* Run this command to build the images: "docker-compose up -d"


## About the installation:  

* __Image:__      jenkins-blueocean:2.401.1
* __Name:__       jenkins-blueocean
* __Data:__       /var/jenkins_home
* __Certs:__      /var/jenkins_home/certs/client:ro
