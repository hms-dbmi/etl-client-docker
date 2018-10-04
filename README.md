# etl-client 

## Installation 

ETL-client 18.1 docker container can be used to load the properly delimited dataset (for example: NHANES)  into i2b2/TM 18.1 compatible database.This etl-client docker image can be deployed using following 2 ways:

* Locally ( on Mac/Linux ) 
  * Docker should up and running 
* On a VM on a cloud vendor like AWS, GCP and Azure
  * perform some [additional steps ](https://github.com/hms-dbmi/etl-client-docker/blob/master/etl-client-AWS-EC2.md) to make the machine(VM/EC2) ready for docker image




#### There are 2 ways you can use this etl-client.
#####Use case 1: 
        
[ETL client with (Quickstart 18.1b stack)](https://github.com/hms-dbmi/etl-client-docker/blob/master/useCase1.md)

#####Use Case 2:

[ETL client with (Struct DB)](https://github.com/hms-dbmi/etl-client-docker/blob/master/useCase2.md)


## Load Data

It is recommeded that you first try loading [example datafiles](https://github.com/hms-dbmi/ETLToolSuite-MappingGenerator/tree/master/example) .


If you already familiar with the process and want to load your custom data file then follow readme for [MappingGenerator](https://github.com/hms-dbmi/ETLToolSuite-MappingGenerator)



## Loading process Overview


* Make sure quickstart DB 18.1 should be up and running
* Get docker container for etl-client-i2b2tm-18.1
* Follow [Steps to Build etl-client-docker](https://github.com/hms-dbmi/etl-client-docker)
 * Validate connections to DB should be successful
* Start with Datafile you want to load 
* Build Initial mapping file using [MappingGenerator](https://github.com/hms-dbmi/ETLToolSuite-MappingGenerator)
* Fix mapping file to match your i2b2 tree and datatypes, try using Mapping Editor (provided) to fix the mapping file
* Run [EntityGenerator](https://github.com/hms-dbmi/ETLToolSuite-MappingGenerator) to generate csv file for each table
* Run [Workflow scripts](https://github.com/hms-dbmi/ETLToolSuite-WorkflowScripts) to load data in your DB
* Run quickstart 18.1 app to point to this DB to validate your load
* Rerun the load ( to refresh database ) 

