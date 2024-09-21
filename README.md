# Nyc-taxi-data-azure-data-engineering-project
In this Project i have  implemented a data engineering solution using all services available on Azure Synapse Analytics to analyze and report data on Taxi Green trips in New York City from 2020 to 2021.

Bussiness Requirements: 

Campaign to encourage credit card payments

    • Trips made using credit card/ Cash payments.

    • Payment behaviour during days of the Week/ Weekend.

    • Payment behaviour between Borough.

Non-Functional Requirements:

    • Reporting data to be pre-aggregated for better performance.

    • Pre-aggregate data for each year/month partition in isolation.

    • Able to read data efficiently for specific months from aggregated data.

    • Minimize the number of aggregated tables created.

About the Dataset:

This dataset contains information about NYC Green trips from 2020 and 2021. -  NYC Green Trip Data

The data was transformed to different file types, and I worked with them in the Synapse Workspace to ingest (Extract), Tranform, and Load data using Serverless Pool:

Dimension Table:

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

     
 Fact Table:

1.Trip Data Green

    •CSV file with Partitioned by Year and Month
    •Parquet file with Partitioned by Year and Month
    •Delta file with Partitioned by Year and Month



![image](https://github.com/user-attachments/assets/45418874-6eda-4948-b4a8-053141a7c91e)


1. Initial Setup:

    • create a database & give collation &UTF
    • create schema for Bronze, Silver, Gold
    • Create External data source ,External File format



2. Create an External table (Bronze):

![image](https://github.com/user-attachments/assets/b087a5de-d145-4421-90cf-54f6f25f14fd)


3. Create a view for Bronze:

![image](https://github.com/user-attachments/assets/6061b4de-b844-401b-b697-65c402606418)


4. (Bronze -Silver) Transformation:

Transform all the CSV Files into Parquet for better Efficiency.

![image](https://github.com/user-attachments/assets/588b1ac2-9f6c-42a0-9a05-0dc7837427e9)


5. Create a view for Silver:

![image](https://github.com/user-attachments/assets/68dea280-273d-4a94-ad47-d4bf65a808a5)


6. (silver -Gold) Transformation:

here, we Join the Tables required,give some cases required.

![image](https://github.com/user-attachments/assets/f93682a9-0de2-4c0f-92fe-6b2089a57a04)


7. create a view for Gold

![image](https://github.com/user-attachments/assets/ac0c9fda-6a9e-435e-8732-55675e19b2c8)



BRONZE – SILVER Transformation using serverless synapse using Pipeline.

1. Create a linked service for ADLS,AZURE SYNAPSE ANALYTICS(serverless).

2. Create a Dataset for ADLS.

3. In the Script activity, write the query for external table.

![alt text](images/image.png)

4. instead of using script activity use stored procedure activity

![alt text](images/image-1.png)

5. instead of creating 7 pipelines,7 datasets we have parameterized the folder path.

![alt text](images/image-2.png)

6. created a silver view by using the stored procedure code already used

![alt text](images/image-3.png)

7. created a gold view by using the stored procedure code already used.

![alt text](images/image-4.png)

8. Execute the pipeline based on our Requirement:

![alt text](images/image-5.png)


9. Execute the pipeline by giving triggers:

![alt text](images/image-6.png)

Conclusion: 

Final data can be used, to effectively encourage credit card payments.

The analysis is segmented by:

    1. Payment Method:
        Compare the frequency and volume of trips made using credit cards versus cash payments.
    2. Day of the Week:
        Analyze payment behaviors during weekdays versus weekends to identify trends and peak times for credit card usage.
    3. Geographical Segmentation:
        Examine payment behaviors across different boroughs to tailor the campaign to specific areas where credit card usage is lower.




















































































