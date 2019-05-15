
# ETL client

## Docker Host Hardware Requirements

* 8GB RAM
* 50GB of free Hard Drive space
* Docker for Mac and Docker for Windows are not supported unless you use docker-machine to create a VM that meets the requirements for RAM and Hard Drive space.

## Use Case 1: ETL client with Database

```

#### Build etl-client-docker
Use "pdbadmin" as DB_USER and "password" as DB_PASSWORD for default values.

```
docker run --name etl-client --network quickstart_public \
		-e DB_HOST=quickstart_db_1 \
		-e DB_USER=<username> \
		-e DB_PASSWORD=<password> \
		-e DB_PORT=1521 \
		-e DB_NAME=orclpdb1 \
		-d   -p 7000:5000  dbmi/etl-client:etl-client-i2b2tm-19.1

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
 
[Load NHANES data subsets example](https://github.com/hms-dbmi/ETLToolSuite-EntityGenerator/blob/master/Example-NHANES.md)

[ETL process overview](https://github.com/hms-dbmi/etl-client-docker)
