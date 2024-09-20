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









