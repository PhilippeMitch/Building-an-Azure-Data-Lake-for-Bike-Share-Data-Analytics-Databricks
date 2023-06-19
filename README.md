# Data Ware House For Bike Share Analytics With Azure Databricks

Divvy is a bike sharing program in Chicago, Illinois USA that allows riders to purchase a pass at a kiosk or use a mobile application 
to unlock a bike at stations around the city and use the bike for a specified amount of time. The bikes can be returned to the same 
station or to another station. The City of Chicago makes the anonymized bike trip data publicly available for projects like this where we can analyze the data.

Since the data from Divvy are anonymous, we have created fake rider and account profiles along with fake payment data to go along with 
the data from Divvy. The dataset looks like this:
![](https://github.com/PhilippeMitch/Building-an-Azure-Data-Lake-for-Bike-Share-Data-Analytics-Databricks/blob/main/images/dend-project-erd.jpeg)

Relational ERD for the Divvy Bikeshare Dataset (with fake data tables)<br>
You will also need the [dataset](https://video.udacity-data.com/topher/2022/March/622a5fc6_azure-data-warehouse-projectdatafiles/azure-data-warehouse-projectdatafiles.zip)
## Project requirements
#### The goal of this project is to develop a data warehouse solution using Azure Synapse Analytics.
* Design a star schema based on the business outcomes listed below;
* Import the data into Synapse;
* Transform the data into the star schema;
* and finally, view the reports from Analytics.
#### The business outcomes you are designing for are as follows:
1. Analyze how much time is spent per ride
   * Based on date and time factors such as day of week and time of day
   * Based on which station is the starting and / or ending station
   * Based on age of the rider at time of the ride
   * Based on whether the rider is a member or a casual rider
2. Analyze how much money is spent
   * Per month, quarter, year
   * Per member, based on the age of the rider at account start
3. EXTRA CREDIT - Analyze how much money is spent per member
   * Based on how many rides the rider averages per month
   * Based on how many minutes the rider spends on a bike per month

#### Star Schema Design
![](https://github.com/PhilippeMitch/Data-Ware-House-For-Bike-Share-Analytics/blob/main/images/udacity.png)


## Project Environment
In order to complete this project, you'll need to use these tools:

* Access to Microsoft Azure.
* Databricks
* Hint: To view your DBFS files, enable the DBFS file browser in Databricks by going to Admin Console -> Workspace Settings -> Advanced
* Hint: If you are going to use PySpark Pandas, make sure you create your Spark Cluster using a Databricks runtime >= 10.0

## Create your Azure resources
* Azure Databricks.

**Note**: 
* If you've previously created a Azure Databricks, you do not need to create a second one specifically for the project.<br>
* If you already have a cloud Databricks account you can only use it as well.

## Upload the data to DBFS
In this step we uploaded the files to DBFS through the workspace.

![](https://github.com/PhilippeMitch/Building-an-Azure-Data-Lake-for-Bike-Share-Data-Analytics-Databricks/blob/main/images/upload%20csv.jpg)

This will result in all four tables being represented as csv files in DBFS, ready to be read and write from.

## Writes out the csv files to Delta file locations.
In this step, we extracted the information from CSV files that we uploaded to DBFS and write it out to the Delta file system.
![](https://github.com/PhilippeMitch/Building-an-Azure-Data-Lake-for-Bike-Share-Data-Analytics-Databricks/blob/main/images/csv_to_delta_files2.jpg)

## Create the tables and then load data from the csv iles
In this step created the tables and loads the data from Delta files. For this taks, we have used spark.sql statements to create the tables 
and then load data from the files that were we extracted from CSV files stored in Databricks and write out to the Delta file system.
![](https://github.com/PhilippeMitch/Building-an-Azure-Data-Lake-for-Bike-Share-Data-Analytics-Databricks/blob/main/images/load_to_tables_2.jpg)

## Transform the data
In this step we transformed the data into the star schema for a Gold data store based on the star diagrams.

![](https://github.com/PhilippeMitch/Building-an-Azure-Data-Lake-for-Bike-Share-Data-Analytics-Databricks/blob/main/images/load_to_star_chema_tables2.jpg)









