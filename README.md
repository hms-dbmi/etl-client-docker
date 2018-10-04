# etl-client 

## Installation 

ETL-client 18.1 docker container can be used to load the properly delimited dataset (for example: NHANES)  into i2b2/TM 18.1 compatible database.This etl-client docker image can be deployed using following 2 ways:

* Locally ( on Mac/Linux ) 
  * Docker should up and running 
* On a VM on a cloud vendor like AWS, GCP and Azure
  * If you are spinning VM on cloud vendor then you have to perform some [additional steps ](https://github.com/hms-dbmi/etl-client-docker/blob/master/etl-client-AWS-EC2.md) to make the machine ready for docker image




#### There are 2 ways you can use this etl-client.
#####Use case 1: 
        
[ETL client with (Quickstart 18.1b stack)](https://github.com/hms-dbmi/etl-client-docker/blob/master/useCase1.md)

#####Use Case 2:

[ETL client with (Struct DB)](https://github.com/hms-dbmi/etl-client-docker/blob/master/useCase2.md)


## Load Data

It is recommeded that you first try loading [example datafiles](https://github.com/hms-dbmi/ETLToolSuite-MappingGenerator/tree/master/example) .


If you already familiar with the process and want to load your custom data file then follow readme for [MappingGenerator](https://github.com/hms-dbmi/ETLToolSuite-MappingGenerator)




