# etl-client 

## Installation 

This etl-client docker image can be deployed using following 2 ways:

* Locally 
  * ( make sure docker is installed, up and running ) 
* On a VM on a cloud vendor like AWS, GCP and Azure
  * If you are spinning VM on cloud vendor then you have to perform some additional steps to make the machine ready for docker image




#### There are 2 ways you can use this etl-client.
* Use case 1: ETL client with (Quickstart 18.1b stack)

https://github.com/hms-dbmi/etl-client-docker/blob/master/useCase1.md

* Use Case 2: ETL client with (Struct DB)

https://github.com/hms-dbmi/etl-client-docker/blob/master/useCase2.md


## Load Data

Link for instructions to load data: https://github.com/hms-dbmi/ETLToolSuite-MappingGenerator


#### If using AWS EC2 for etl then follow the steps below to prepare EC2

```
sudo yum update -y

sudo yum install git

sudo yum install -y docker

sudo usermod -a -G docker ec2-user

sudo curl -L https://github.com/docker/compose/releases/download/1.22.0/docker-compose-`uname -s-uname -m` | sudo tee /usr/local/bin/docker-compose > /dev/null

sudo chmod +x /usr/local/bin/docker-compose

sudo service docker start

sudo chkconfig docker on

exit

```

