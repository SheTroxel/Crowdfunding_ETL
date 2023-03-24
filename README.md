# Crowdfunding_ETL

This project contains four mini projects and has been done in collaboration with Nancy Gomez, Leah Apking, and Erin Clark. The project is designed to provide practice in building an ETL pipeline using Python, Pandas, and either Python dictionary methods or regular expressions to extract and transform the data. 

The project has been divided into four mini-projects:

 - Create the Category and Subcategory DataFrames
 - Create the Campaign DataFrame
 - Create the Contacts DataFrame
 - Create the Crowd Funding Database
 
 ### Created a Category and Subcategory DataFrame 
 
#### category_df
Extracted and transformed data from the crowdfunding.xlsx Excel file to create a category DataFrame 

The category DataFrame consists of two columns: 

- The category_id column list entries sequentially from cat 1 to catn, where n is the unique number of categories.

- The category column contains only the category titles. 

Exported the category DataFrame as category.csv 

#### subcategory_df

Extracted and transformed data from the crowdfunding.xlsx Excel file to create a category DataFrame 

The category DataFrame consists of two columns: 

- The subcategory_id column list entries sequentially from subcat 1 to subcatn, where n is the unique number of subcategories.

- The subcategory column contains only the subcategory titles. 

Exported the subcategory DataFrame as subcategory.csv 


### Creating the Campaign DataFrame
Extracted and transformed data from the crowdfunding.xlsx Excel file to create a campaign DataFrame with the following columns:

- The "cf_id" column
- The "contact_id" column
- The "company_name" column
- The "blurb" column, renamed to "description"
- The "goal" column, converted to the float data type
- The "pledged" column, converted to the float data type
- The "outcome" column
- The "backers_count" column
- The "country" column
- The "currency" column
- The "launched_at" column, renamed to "launch_date" and with the UTC times converted to the datetime format
- The "deadline" column, renamed to "end_date" and with the UTC times converted to the datetime format
- The "category_id" column, with unique identification numbers matching those in the "category_id" column of the category DataFrame
- The "subcategory_id" column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame


### Create the Contacts DataFrame
In this project, we had the options to choose one of the following two options for extracting and transforming the data from the contacts.xlsx Excel data:

- Option 1: Use Python dictionary methods.
- Option 2: Use regular expressions.

For this section, our group took different routes. Some choose to use the Python dictionary methods while some opted for option 2. Most of my work on this project was spent on the first two sections and the following postgres SQL section, as I have a fondness for ERD diagrams and schemas. This section is largely done in collaboration with Nancy Gomez and Leah Apking. I chose the second option because it would provide me with more practice in this area.

To start, we imported the contact.xlsx file into a DataFrame, extracted the “contact_id”, “name”, and “email” columns using regular expressions to create a new DataFrame. From here we converted the “contact_id” column to the integer type, split each “name” column into a first and a last name, and placed each in a new column. Once cleaned, we then exported the DataFrame as contacts.csv


### Create the Contacts DataFrame
In this project we had the options to choose one of the following two options for extracting and transforming the data from the contacts.xlsx Excel data:

- Option 1: Use Python dictionary methods.
- Option 2: Use regular expressions.

For this part of the project, our collaboration group took different routes. Some choose to use the Python dictionary methods while some opted for option 2. Most of my work on this project was spent on the first two sections and the postgres SQL section as I have a fondness for ERD diagrams. This section is largely done in collaboration with Nancy Gomez and Leah Apking. I chose the second option because it would provide more we more practice in this area.

For this section, we imported the contact.xlsx file into a DataFrame, extracted the “contact_id”, “name”, and “email” columns using regular expressions to create a new DataFrame. From here we converted the “contact_id” column to the integer type, split each “name” column into a first and a last name, and placed each in a new column. Once cleaned, we then exported the DataFrame as contacts.csv


###Create the Crowdfunding Database

For this section, I inspected the four CSV files, and then sketch an ERD of the tables by using QuickDBDLinks (https://www.quickdatabasediagrams.com/) 

![schema]( https://github.com/SheTroxel/Crowdfunding_ETL/blob/main/QuickDBD-crowdfunding_db_schema.png)

Using the information from the ERD,  I created a table schema for each CSV file making sure to specify the data types, primary keys, foreign keys, and other constraints. Using the schema, I created tables in correct order to handle foreign keys and was able to verfity table creating by running a SELECT statement for each table. 

![queryschema]( https://github.com/SheTroxel/Crowdfunding_ETL/blob/main/QuickDBD-crowdfunding_db_schema.sql)

Once tables were created, I imported each CSV file into its corresponding SQL table and verified that everything imported correctly.


![verification]( https://github.com/SheTroxel/Crowdfunding_ETL/blob/main/verificationcode.sql)

