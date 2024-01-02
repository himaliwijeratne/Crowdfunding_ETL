# Crowdingfunding_ETL
The instructions for this mini project are divided into the following subsections:

  1) Create the Category and Subcategory DataFrames
  2) Create the Campaign DataFrame
  3) Create the Contacts DataFrame
  4) Create the Crowdfunding Database

Create the Category and Subcategory DataFrames
    A) Extract and transform the crowdfunding.xlsx Excel data to create a category DataFrame that has the following columns:

    A "category_id" column that has entries going sequentially from "cat1" to "catn", where n is the number of unique categories

    A "category" column that contains only the category titles

    The following image shows this category DataFrame:

  ![image](https://github.com/gsd002/Crowdingfunding_ETL/assets/144679119/d844dbae-89aa-4bfd-9903-215410f486d1)

    B) Export the category DataFrame as category.csv and save it to your GitHub repository.

    C) Extract and transform the crowdfunding.xlsx Excel data to create a subcategory DataFrame that has the following columns:

    A "subcategory_id" column that has entries going sequentially from "subcat1" to "subcatn", where n is the number of unique subcategories

    A "subcategory" column that contains only the subcategory titles

    The following image shows this subcategory DataFrame:

  ![image](https://github.com/gsd002/Crowdingfunding_ETL/assets/144679119/185c9ef1-117f-425c-a0c0-034847d7aedc)

    D) Export the subcategory DataFrame as subcategory.csv and save it to your GitHub repository.

Create the Campaign DataFrame
    A) Extract and transform the crowdfunding.xlsx Excel data to create a campaign DataFrame has the following columns:

      The "cf_id" column
      The "contact_id" column
      The "company_name" column
      The "blurb" column, renamed to "description"
      The "goal" column, converted to the float data type
      The "pledged" column, converted to the float data type
      The "outcome" column
      The "backers_count" column
      The "country" column
      The "currency" column
      The "launched_at" column, renamed to "launch_date" and with the UTC times converted to the datetime format
      The "deadline" column, renamed to "end_date" and with the UTC times converted to the datetime format
      The "category_id" column, with unique identification numbers matching those in the "category_id" column of the category DataFrame
      The "subcategory_id" column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame

      The following image shows this campaign DataFrame:
  ![image](https://github.com/gsd002/Crowdingfunding_ETL/assets/144679119/d31daf3e-8700-4915-9d35-77ca9ecb496c)

    B) Export the campaign DataFrame as campaign.csv and save it to your GitHub repository.

Create the Contacts DataFrame
    Choose one of the following two options for extracting and transforming the data from the contacts.xlsx Excel data:
    Option 1: Use Python dictionary methods.
    Option 2: Use regular expressions.
  
    Using Option 1: Use Python dictionary methods.
  
    a) Import the contacts.xlsx file into a DataFrame.
    b) Iterate through the DataFrame, converting each row to a dictionary.
    c) Iterate through each dictionary, doing the following:
    d) Extract the dictionary values from the keys by using a Python list comprehension.
    e) Add the values for each row to a new list.
    f) Create a new DataFrame that contains the extracted data.
    g) Split each "name" column value into a first and last name, and place each in a new column.
    h) Clean and export the DataFrame as contacts.csv and save it to your GitHub repository.
  
  ![image](https://github.com/gsd002/Crowdingfunding_ETL/assets/144679119/ffa28bbb-9132-498e-a019-14661d2bd23b)

Create the Crowdfunding Database
  1) Inspect the four CSV files, and then sketch an ERD of the tables by using QuickDBDLinks to an external site..
  2) Use the information from the ERD to create a table schema for each CSV file.
     Note: Remember to specify the data types, primary keys, foreign keys, and other constraints.
  3) Save the database schema as a Postgres file named crowdfunding_db_schema.sql, and save it to your GitHub repository.
  4) Create a new Postgres database, named crowdfunding_db.
  5) Using the database schema, create the tables in the correct order to handle the foreign keys.
  6) Verify the table creation by running a SELECT statement for each table.
  7) Import each CSV file into its corresponding SQL table.
  8) Verify that each table has the correct data by running a SELECT statement for each.

Hints
    To split each "category & sub-category" column value into "category" and "subcategory" column values, use df[["new_column1","new_column2"]] = df["column"].str.split(). Make sure to pass the correct parameters to the split() function.
    
    To get the unique category and subcategory values from the "category" and "subcategory" columns, create a NumPy array where the array length equals the number of unique categories and unique subcategories from each column. For information about how to do so, see numpy.arangeLinks to an external site. in the NumPy documentation.
    
    To create the category and subcategory identification numbers, use a list comprehension to add the "cat" string or the "subcat" string to each number in the category or the subcategory array, respectively.
    
    For more information about creating a new Pandas DataFrame, see the pandas.DataFrameLinks to an external site. in the Pandas documentation.
    
    To convert the "goal" and "pledged" columns to the float data type, use the astype() method.
    
    To convert the "launch_date" and "end_date" UTC times to the datetime format, see the Transform_Grocery_Orders_Solved.ipynb activity solution.
    
    For more information about how to add the "category_id" and "subcategory_id" unique identification numbers to the campaign DataFrame, see the pandas.DataFrame.mergeLinks to an external site. in the Pandas documentation.
