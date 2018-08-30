# etl-client 


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

##### Application expects you to provide Database and AWS keys

edit  etl-client-docker.env

```
# database

DB_HOST=
DB_USER=
DB_PASSWORD=
DB_PORT=
DB_NAME=

APP_PORT=7000

# aws

AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_REGION= 
```

##### run the container

```
docker-compose build && docker-compose up -d
```


#####  bash into the container

```
docker exec -it etl-client bash
```


#####  validate your database and aws configurations
```
cd /etl-workdir
python3  validate_conn.py 
```


##### url

```
http://<hostname>:7000/
```
