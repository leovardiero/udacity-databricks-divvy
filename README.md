# Project Overview
Divvy is a bike sharing program in Chicago, Illinois USA that allows riders to purchase a pass at a kiosk or use a mobile application to unlock a bike at stations around the city and use the bike for a specified amount of time. The bikes can be returned to the same station or to another station. The City of Chicago makes the anonymized bike trip data publicly available for projects like this where we can analyze the data.

Since the data from Divvy are anonymous, we have created fake rider and account profiles along with fake payment data to go along with the data from Divvy. The dataset looks like this:

![Divvy ERP](./images/divvy-erd.jpeg)

The goal of this project is to develop a data lake solution using Azure Databricks using a lake house architecture. You will:

* Design a star schema based on the business outcomes below;
* Import the data into Azure Databricks using Delta Lake to create a Bronze data store;
* Create a gold data store in Delta Lake tables;
* Transform the data into the star schema for a Gold data store;

### Required Analysis

The business outcomes you are designing for are as follows:

#### 1. Analyze how much time is spent per rid
* Based on date and time factors such as day of week and time of day
* Based on which station is the starting and / or ending station
* Based on age of the rider at time of the ride
* Based on whether the rider is a member or a casual rider

#### 2. Analyze how much money is spent
* Per month, quarter, year
* Per member, based on the age of the rider at account start

#### 3. EXTRA CREDIT - Analyze how much money is spent per member
* Based on how many rides the rider averages per month
* Based on how many minutes the rider spends on a bike per month

## Data 

The data used for this project can be downloaded at [Divvy Data](https://video.udacity-data.com/topher/2022/March/622a5fc6_azure-data-warehouse-projectdatafiles/azure-data-warehouse-projectdatafiles.zip).

## Steps

### 1. Design Star Schema

The firt step is design the Star Schema based on Required Analysis, based on the ERP. The result is the following:

![Divvy ERP](./images/StarSchema.png)

### 2. Import Data into Azure Databricks

The 4 datasets was loaded into Azure Databricks, on landing zone:

![Data on Databricks](./images/data_on_azure.jpg)

Then, the code present on Jupyter Notebook `./Scripts/01. Extract.ipynb` was ran to create the Bronze data store.

### 3. Import Data into Azure Databricks

The scripts `./Scripts/02. Load.ipynb` and `./Scripts/03. Transform.ipynb` contains the script to create the gold store and transform the bronze data into the Star Schema.