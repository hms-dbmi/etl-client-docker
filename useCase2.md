



# ETL client 

## Use case 2: ETL client with (Quickstart 18.1b stack)

In this case quickstart stack is up and running and you are loading data in existing DB. 
Please note that scripts truncate and reload the tables.

Just follow the steps:
* Build et-client-docker
* Validate Oracle database connection 


If there is Quickstart 18.1 (app and db) - want to try with existing database.
 
####  Assuming there is an database up and running (Quickstart 18.1 db)


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
### Validate Oracle database connection

```
docker exec -it etl-client bash validate-db.sh 
```
