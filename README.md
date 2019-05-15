# etl-client

etl-client 19.1 is deployed as docker container and can be used to load the properly delimited dataset (for example: NHANES data publicly available)  into i2b2/TM 19.1 compatible database. Once you are familiar with the process then you can use it load any clinical datafile in i2b2/tranSMART 19.1 database. Our process has been tested extensively on Oracle databases so if you are running any database the please adjust the enviornment accordingly.

## DISCLAIMER:
### The data loader truncate and reload the i2b2demodata/i2b2metadata schema tables.
Please double check before running any data loaders in production environment.



![ETL Client Oevreview](https://github.com/hms-dbmi/etl-client-docker/blob/master/etl-client-19.1.png)

## Installation

This etl-client docker image can be deployed using following 2 ways:

* Locally ( on Mac/Linux )
  * Docker should up and running
* On a VM on a cloud vendor like AWS, GCP and Azure
  * perform some [additional steps ](https://github.com/hms-dbmi/etl-client-docker/blob/master/etl-client-AWS-EC2.md) to make the machine(VM/EC2) ready for docker image




#### There are 2 ways you can use this etl-client.

##### Use Case 19.1 ( preferred if you are loading your own data in production with 19.1 stack):

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ETL client with (Struct DB)](https://github.com/hms-dbmi/etl-client-docker/blob/master/useCase-19.1.md)




##### Use case (Quickstart 18.1b):

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ETL client with (Quickstart 18.1b stack)](https://github.com/hms-dbmi/etl-client-docker/blob/master/useCase1.md)

This option can be used if you are still using the Quickstart 18.1b stack.



## Data Loading Overview

It is recommended that you first try loading [example datafiles](https://github.com/hms-dbmi/ETLToolSuite-MappingGenerator/tree/master/example) .


If you already familiar with the process and want to load your custom data file then just follow the steps below.

* Make sure i2b2/tranSMART DB 19.1 is up and running.
* Install etl-client-docker  - container should be up and running ( follow above installation instructions)
* Validate connections to DB -  should be Successful
* Start with Datafile you want to load
* Build Initial mapping file using [MappingGenerator](https://github.com/hms-dbmi/ETLToolSuite-MappingGenerator)
* Fix mapping file to match your i2b2 tree and datatypes, try using Mapping Editor (provided) to fix the mapping file
* Run [EntityGenerator](https://github.com/hms-dbmi/ETLToolSuite-EntityGenerator) to generate csv file for each table
* Run [Workflow scripts](https://github.com/hms-dbmi/ETLToolSuite-WorkflowScripts) to load data in your DB
* Test your i2b2/tranSMART application with latest data loaded.


## Example to load NHANES dataset subsets

* small ~ 100 patients
* large ~ 5k patients

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Load NHANES data subsets example](https://github.com/hms-dbmi/ETLToolSuite-EntityGenerator/blob/master/Example-NHANES.md)
