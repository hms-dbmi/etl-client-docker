



# ETL client with (Quickstart 18.1): (use case 2)


## If there is Quickstart 18.1 (app and db) - want to try with existing database.
 
###  Assuming there is an database up and running (Quickstart 18.1 db)

```
docker run --name etl-client --network quickstart_public \
		-e DB_HOST=<hostname> \
		-e DB_USER=<username> \
		-e DB_PASSWORD=<password> \
		-e DB_PORT=<port> \
		-e DB_NAME=<databasename> \
		-d   -p 7000:5000  dbmi/etl-client:etl-client-i2b2tm-18.1 
```
### To validate oracle database connection

```
docker exec -it etl-client bash validate-db.sh 
```
