# HousingDataset_Analysis
Data analytics project done with python with help of Pandas, SQLite, Flask. 
HousingDataset file is uploaded on my drive, I am putting the drive link so that you can download the file to work on your local system.
Dataset Drive URL :- https://drive.google.com/file/d/115p8LlkQ_2Bg99s8jK50Ifao3ZF68SZ1/view?usp=drive_link
First step is to import the dataset in the colab notebook environment.

Section 1: Environment setup and data cleaning

Please read the records from the csv file and create a DataFrame(DF) . Clean the DF using the following steps:
• Identify and remove the following columns:
a. ad_type
b. title
c. description
d. l4
e. l5
f. l6
• Investigate and discard all rows that contain Null values in any of these fields:
a. lon
b. lat
c. price_period
d. bedrooms
e. surface_total
f. rooms
g. price
h. surface_covered

• Once cleaning is done, separate the DF into 2 Tables. One with property_details and another with property_price_details
and load them into SQL database on your local (Ex. SQLite, sqlalchemy). Columns for each should be given as mentioned
below.

Property_Details columns: id, start_date, end_date, created_on, lat, lon, l1, l2, l3, rooms, bedrooms, bathrooms,
surface_total, surface_covered
Property_Price_Details columns: id, price, currency, price_period, property_type, operation_type

Section 2: Data Analysis

Use the cleaned local database to fetch the following results:
• Retrieve properties that have a price greater than 1 million and are located in "Estados Unidos" (l1).
• Categorize properties based on their surface area as 'Small' if it's less than 50 square meters, 'Medium' if it's
between 50 and 100 square meters, and 'Large' if it's greater than 100 square meters:
• List all properties (id) in the "Belgrano" neighborhood (l3) that have the same number of bedrooms and
bathrooms as another property in the dataset:
• Calculate the average price per square meter (price / surface_total) for each property type (property_type) in
the "Belgrano" neighborhood (l3):
• Identify properties that have a higher price than the average price of properties with the same number of
bedrooms and bathrooms.
• Calculate the cumulative price for each property type, ordered by the creation date.
• Identify the 10 locations (l3) with the highest total surface area (sum of surface_total) of properties listed for
sale (operation_type = 'Venta'):
• Find the top 5 most expensive properties (based on price) in the "Palermo" neighborhood (l3) that were listed
in August 2020:
• Find the top 3 properties with the highest price per square meter (price divided by surface area) within each
property type.
• Find the top 3 locations (l1, l2, l3) with the highest average price per square meter (price / surface_total) for
properties listed for sale (operation_type = 'Venta') in the year 2020. Exclude locations with fewer than 10
properties listed for sale in 2020 from the results.

Section 3: Expose the results in API

• Create API endpoints for the 10 questions in Section 2 and print the results as the API response.
• You only need to implement the GET HTTP method. The method names will be like /question-1
• The API methods will be the question number and it should return the results. (Please hardcode the results you
received from Sec2) Example of API calls: http://127.0.0.1:6000/question-4
• The API should do some basic error handling. Example: Invalid Question Number.
