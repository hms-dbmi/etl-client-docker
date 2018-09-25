# etl-client 

## Installation 

This etl-client docker image can be deployed using following 2 ways:

* Locally 
  * ( make sure docker is installed, up and running ) 
* On a VM on a cloud vendor like AWS, GCP and Azure
  * If you are spinning VM on cloud vendor then you have to perform some additional steps to make the machine ready for docker image


#### Prepare machine (aws)

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


#### Get the etl-client-docker 

clone the repository


```
git clone https://github.com/hms-dbmi/etl-client-docker.git etl-client-docker
```


change directory to  etl-client-docker

```
cd  etl-client-docker
```
## Configuration
##### Application expects you to provide Database and AWS keys

edit  etl-client-docker.env

```
# database

DB_HOST=<DB_HOST>
DB_USER=<DB_USER>
DB_PASSWORD=<DB_PASSWORD>
DB_PORT=<DB_PORT>
DB_NAME=<DB_NAME>

# aws

AWS_ACCESS_KEY_ID=<AWS_ACCESS_KEY_ID>
AWS_SECRET_ACCESS_KEY=<AWS_SECRET_ACCESS_KEY>
AWS_REGION=<AWS_REGION>
```
## Start Container
##### run the container

```
docker-compose up -d
```


#####  bash into the container

```
docker exec -it etl-client bash
```

## Validation ( for configuration) 
You can run the following command to make sure your connections to database is valid 
```
docker exec -it etl-client bash validate-db.sh 
```

## Load Data

Link for instructions to load data: https://github.com/hms-dbmi/ETLToolSuite-MappingGenerator

