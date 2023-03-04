# PIZZA SALES ANALYSIS - 2015

![](New_Pizza.jpg)

## Introduction

I often wonder if am the only one who finds pizza simply irresistible.Its a go to when you need an easy meal at home or even for an office event.My favorites remains the BBQ Chicken Pizza and the Pepperoni Pizza.I was looking for a dataset to get my hands dirty with and i came across this dataset from Quantum Analytics and for the love of Pizza i jump on it and i found it rich with insights.

*__Disclaimer__* : _All datasets and reports do not represent any company,institution, or country but just a dummy dataset to demonstrate the capabilities of PowerBI._
#### PowerBI Concepts Applied:
DAX, Calculated Columns, Quick Measures,Slicers.

## Problem Statement

The Stakeholders have requested the following Insights on the dashboard:
- Total Revenue
- Total Orders
- Number of Pizza Category
- Total Quantity
- Revenue by Category
- Best selling Pizza (Top 5)
- Revenue trend by Day of the Week
- Orders and Quantities by Day of the week
- Quantity sold by Pizza size
- Time of the day with highest Sales.

## Data Sourcing

After effectively communicating with the Stakeholders to clearly understand their reporting requirements and expectations i went ahead to source for the data. internally.I then downloaded the excel file studied it properly to understand the dataset before extracting in to PowerBI for Cleaning, Modelling, Analysis and Visualization.

The downloaded Excel file is a structured data and made up of 4 tables (Sheets) as follows:

Table 1. ORDERS - With 21,351 rows and 4 Columns.

Table 2. PIZZA PRICE - With 97 rows and 4 Columns.

Table 3. ORDER DETAILS - With 48,621 rows and 4 Columns.

Table 4. PIZZA TYPES - With 33 rows and 4 Columns.

## Data Transformation/Cleaning :

The four tables were then loaded on Power Query editor of POWERBI where Table 2-4 were merged (Join) into Table one using the Primary and Foreign keys for the join and only Table one loaded on POWERBI  .see screen shot below:

<img width="527" alt="Table_Merging" src="https://user-images.githubusercontent.com/119946458/222804752-dc3e2d14-acfb-4d2e-9322-0f4edcae2fee.png">


Also to clean and transform the data after merging some of the applied steps taken included;

- Promoting first row as header in the ORDER Table.
- Amending the header name for Price as Unit Price.
- Created a custom column for "Actual Price" using custom column formular Actual Price = [Unit price]*[quantity] data type changed from to whole numbers.
- Data Type was changed from decimal to whole numbers.
- Created a new measure to calculate the Total revenue,Total Order and Total Quantity sold using the below DAX Formular; - 

  TOTAL REVENUE = SUM(Orders[Actual Price])
  
  TOTAL ORDER   = COUNT(Orders[order_id])
  
  TOTAL QTY SOLD= SUM(Orders[quantity])
 - Transform date in a new column to "Name of days" and also "days of week"
 - Created a new column with the time column provided using the DAX formular - Time Of The Day = IF(Orders[time] < 12, "MORNING", "AFTERNOON")
 - Created a new column to show the various time of the day using DAX see syntax below;
  
  <img width="660" alt="Time Dax" src="https://user-images.githubusercontent.com/119946458/222837142-b1c90465-6d33-4ea7-83de-5aab347317e5.png">
  
 - Close and apply steps.

## Data Modelling

Since i already merged the tables into a single table fom the start there was no data modelling to be done.

<img width="406" alt="Data Modelling" src="https://user-images.githubusercontent.com/119946458/222838225-f4586d27-b99b-4457-911e-a6c576759e85.png">

## Data Analysis and Visuals

<img width="596" alt="Pizza_Dashboard" src="https://user-images.githubusercontent.com/119946458/222840343-cd451519-5402-4f0b-b283-2374984cd639.png">

The report consist of 3 pages. 

You can interact with the report [here](https://app.powerbi.com/groups/me/reports/a477f852-cba1-4eca-bbc4-fc7adfeb5bbc/ReportSection)

From the Analysis conducted the following insights were gotten
1. The Total Revenue for the year 2015 was £815k
2. The Pizza company makes 32 varieties of Pizza which is divided into 4 category 
3. For the year 2015 they sold a Total Quantity of 50,000 (50K) from the Total of 49,000 order made.
4. The Revenue analysis shows an upward trend during the weekdays and a downward trend during the weekends with peak of sale on Fridays.This explains the most profitable days for the pizza company which is likely because it is located in a busy enviroment surrounded by Working professionals and Students.See screenshots below.

<img width="636" alt="Revenue_Trend" src="https://user-images.githubusercontent.com/119946458/222899538-8318bdaf-f126-4120-90a2-80759b79379a.png">










