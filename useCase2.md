
# ETL client

## Docker Host Hardware Requirements

* 8GB RAM
* 50GB of free Hard Drive space
* Docker for Mac and Docker for Windows are not supported unless you use docker-machine to create a VM that meets the requirements for RAM and Hard Drive space.

## Use Case 2: ETL client with (Struct DB)

If there is no Quickstart 18.1 (app and db) and you just want to load the data in database. Just follow the steps:
* Setup Docker machine
* Create working directory
* Create Network
* Build quickstart database structure only - no data.
* Build etl-client-docker
* Validate Oracle database connection 

#### Setup Docker machine
```docker-machine create --driver=virtualbox --virtualbox-cpu-count -8 --virtualbox-disk-size 65000 --virtualbox-memory 8192 i2b2tm```

```eval $(docker-machine env i2b2tm)```


#### Create working directory

```mkdir etl-client```

```cd etl-client```

#### Create network
```
docker network create quickstart_public
```

#### Build QS database structure only - no data.
```
docker run --name quickstart_db_1 --network quickstart_public -d   -p 1521:1521  dbmi/i2b2transmart-db:oracle.12.2.0.1-ee-i2b2.1.7.09-tm.release-18.1-v1.5-struct-only 
```

#### Build etl-client-docker 
```
docker run --name etl-client --network quickstart_public \
		-e DB_HOST=<hostname> \
		-e DB_USER=<username> \
		-e DB_PASSWORD=<password> \
		-e DB_PORT=<port> \
		-e DB_NAME=<databasename> \
		-d   -p 7000:5000  dbmi/etl-client:etl-client-i2b2tm-18.1 

```

#### Validate Oracle database connection
You can run the following command to make sure your connections to database is valid 
```
docker exec -it etl-client bash validate-db.sh 
```



## Perform Dataload in DB schema

Example to load NHANES dataset subsets 

* small ~ 100 patients
* large ~ 5k patients

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Load NHANES data subsets example](https://github.com/hms-dbmi/ETLToolSuite-EntityGenerator/blob/master/Example-NHANES.md)

[ETL process overview](https://github.com/hms-dbmi/etl-client-docker)

#### Clone the Quickstart Application (with out database)

```
git clone https://github.com/hms-dbmi/i2b2tmapp-quickstart.git  i2b2tmapp-quickstart

cd i2b2tmapp-quickstart

docker-compose up -d

```
