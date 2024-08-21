# ETL mini project (Project 2 )

For this ETL mini-project, you will collaborate with a partner to build an ETL pipeline using Python and Pandas, incorporating either dictionary methods or regular expressions for data extraction and transformation. After transforming the data, you will create four CSV files, which will be used to develop an Entity-Relationship Diagram (ERD) and define a table schema. Finally, you will load the data from the CSV files into a PostgreSQL database.

### Instructions

The instructions for this mini project are divided into the following subsections:

Create the Category and Subcategory DataFrames

Create the Campaign DataFrame

Create the Contacts DataFrame

Create the Crowdfunding Database

### Create the Category and Subcategory DataFrames:

We created a Category DataFrame with two columns: "category_id," which is sequentially numbered from 1 to match the number of unique categories, and "category," which contains the category names. We then exported this DataFrame as a CSV file named category.csv. Similarly, we built a SubCategory DataFrame with "subcategory_id" sequentially numbered to match the unique subcategories, and "subcategory" containing the subcategory names. This DataFrame was also exported as a CSV file named subcategory.csv.

![Catergory_Subcategory](https://i.postimg.cc/fy58MLCy/Category-and-Subcategory.png)

### Create the Campaign DataFrame:

We extracted and transformed the data from the crowdfunding.xlsx Excel file to create a campaign DataFrame with the required columns. We included "cf_id," "contact_id," and "company_name," while renaming the "blurb" column to "description." We converted both the "goal" and "pledged" columns to the float data type, and retained the "outcome," "backers_count," "country," and "currency" columns. We also renamed "launched_at" to "launch_date" and "deadline" to "end_date," converting the UTC times to datetime format. Additionally, we added "category_id" and "subcategory_id" columns, aligning them with the unique identifiers in the corresponding Category and SubCategory DataFrames. The following image shows this campaign DataFrame:

![Campaign_DataFrame](https://i.postimg.cc/FFGpdYbs/Campaign-Data-Frame.png)

### Create the Contacts DataFrame:

We imported the contacts.xlsx file into a DataFrame, then iterated through the DataFrame, converting each row into a dictionary. Using a Python list comprehension, we extracted the dictionary values from the keys and compiled the values into a new list for each row. From this, we created a new DataFrame containing the extracted data. We then split the "name" column into separate first and last name columns, ensuring that each was placed correctly. Finally, we cleaned the DataFrame and exported it as contacts.csv, saving it to our GitHub repository. The following images shows the final DataFrame contact list:

![DataFrame_Contact_List](https://i.postimg.cc/J4vbZZsm/Data-Frame-Contact-List.png)

### Create the Crowdfunding Database:

We began by inspecting the four CSV files and sketched an ERD using QuickDBD to visualize the relationships between the tables. Using the ERD, we created a table schema for each CSV file, specifying data types, primary keys, foreign keys, and other constraints. We then saved this schema as a Postgres file named crowdfunding_db_schema.sql and committed it to our GitHub repository. The follwoing images shows our ERD and our exported crowdfunding_db_schema:

![ERD](https://github.com/mariemsdiaz/Crowdfunding_ETL/blob/main/Resources/ERD_Table.png)

![Crowdsunding_db_schema](https://i.postimg.cc/bvHb753N/Crowfunding-db-schema.png)

Next, we created a new Postgres database called crowdfunding_db and, following the schema, created the tables in the correct order to manage foreign keys. To ensure the tables were created correctly, we ran SELECT statements for each table. Finally, we imported each CSV file into its corresponding SQL table and verified the accuracy of the data with SELECT statements for each table.

We successfully built and validated an ETL pipeline, transforming data into organized CSV files, developing a PostgreSQL database, and ensuring data accuracy through thorough verification.


