# nyc-taxi-data-azure-data-engineering-project
In this Project i have  implemented a data engineering solution using all services available on Azure Synapse Analytics to analyze and report data on Taxi Green trips in New York City from 2020 to 2021.

About the Dataset:

This dataset contains information about NYC Green trips from 2020 and 2021. -  NYC Green Trip Data

The data was transformed to different file types, and I worked with them in the Synapse Workspace to ingest (Extract), Tranform, and Load data using Serverless Pool:

Dimension Table

  1.Taxi Zone
  
      • CSV file with header
      • CSV file without header
      
  2.Calendar
  
      • CSV file
      
  3.Vendor
  
      •CSV file
      •CSV file with escaped characters( \ )
      •CSV file with unquote (" ")
      
  4.Rate Code
  
      •JSON file

  5.Trip Type
  
     •TSV, Tab-Separated
     
  6.Payment Type
  
     •JSON file
     •JSON file with array

     
 Fact Table

1.Trip Data Green

    •CSV file with Partitioned by Year and Month
    •Parquet file with Partitioned by Year and Month
    •Delta file with Partitioned by Year and Month



![image](https://github.com/user-attachments/assets/45418874-6eda-4948-b4a8-053141a7c91e)


1. Initial Setup:




Create an External table (Bronze):

![image](https://github.com/user-attachments/assets/b087a5de-d145-4421-90cf-54f6f25f14fd)


Create a view for Bronze:

![image](https://github.com/user-attachments/assets/6061b4de-b844-401b-b697-65c402606418)


(Bronze -Silver) Transformation:

![image](https://github.com/user-attachments/assets/588b1ac2-9f6c-42a0-9a05-0dc7837427e9)


Create a view for Silver:

![image](https://github.com/user-attachments/assets/68dea280-273d-4a94-ad47-d4bf65a808a5)


![image](https://github.com/user-attachments/assets/f93682a9-0de2-4c0f-92fe-6b2089a57a04)


create a view for Gold

![image](https://github.com/user-attachments/assets/ac0c9fda-6a9e-435e-8732-55675e19b2c8)



BRONZE – SILVER Transformation using serverless synapse using Pipeline.




























































































