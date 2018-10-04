# etl-client 

etl-client 18.1 is deployed as docker container and can be used to load the properly delimited dataset (for example: NHANES data publicly available)  into i2b2/TM 18.1 compatible database. Once you are familiar with the process then you can use it load any clinical datafile in i2b2/tranSMART 18.1 database. 



![ETL Client Oevreview](https://github.com/hms-dbmi/etl-client-docker/blob/master/ETL-client-overview.png)

## Installation 

This etl-client docker image can be deployed using following 2 ways:

* Locally ( on Mac/Linux ) 
  * Docker should up and running 
* On a VM on a cloud vendor like AWS, GCP and Azure
  * perform some [additional steps ](https://github.com/hms-dbmi/etl-client-docker/blob/master/etl-client-AWS-EC2.md) to make the machine(VM/EC2) ready for docker image




#### There are 2 ways you can use this etl-client.
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;##### Use case 1: 
        
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ETL client with (Quickstart 18.1b stack)](https://github.com/hms-dbmi/etl-client-docker/blob/master/useCase1.md)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;##### Use Case 2:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ETL client with (Struct DB)](https://github.com/hms-dbmi/etl-client-docker/blob/master/useCase2.md)



## Data Loading Overview

It is recommeded that you first try loading [example datafiles](https://github.com/hms-dbmi/ETLToolSuite-MappingGenerator/tree/master/example) .


If you already familiar with the process and want to load your custom data file then just follow the steps below.

* Make sure quickstart DB 18.1 is up and running
* Install etl-client-docker  - container should be up and running ( follow above installation instructions) 
* Validate connections to DB -  should be Successful
* Start with Datafile you want to load 
* Build Initial mapping file using [MappingGenerator](https://github.com/hms-dbmi/ETLToolSuite-MappingGenerator)
* Fix mapping file to match your i2b2 tree and datatypes, try using Mapping Editor (provided) to fix the mapping file
* Run [EntityGenerator](https://github.com/hms-dbmi/ETLToolSuite-MappingGenerator) to generate csv file for each table
* Run [Workflow scripts](https://github.com/hms-dbmi/ETLToolSuite-WorkflowScripts) to load data in your DB
* Run [quickstart 18.1 app](https://github.com/i2b2-tranSMART/i2b2transmart-quick-start) to point to this DB to validate your load

## Example to load NHANES dataset subsets 

* small ~ 100 patients
* large ~ 5k patients

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Load NHANES data subsets example](https://hms-dbmi.atlassian.net/wiki/spaces/AVL/pages/621183053/Quick+Start+ETL+Examples)

