# data_migration
This is a powerful tool for migrating data from an old system to a new system.
It's for php web based applicaions using mysql for database
though you are free to customize it to fit your needs.
## How it works
### Step 1 (Creating Data)
  - Export your old database tables into csv files. For the case of new data just make sure it's in the csv format.
  - If you have data stored in an excel sheet, you can also convert it to a comma delimitted csv file.
  - Go to step 2.
### Step 2 (Uploading Data)
  - When you have the csv file(s) with your data you now need to know
  how the columns in the csv file map to the columns in the tables of your database tables.
  For simplicity we expect a file to feed one table though you can have one file feeding more than one table in the database.
  - For the start we haven't made a composer package for the project, so you will need to copy this folder to your project folder in the root folder.
  - Then vist base_url/data_migration/upload_data.php
  - You will be prompted to upload the csv files, then the back end will parse the files for you
  then generate for you some interface for table mappings to enable you migrate data to the right tables.
  - In cases where you have to files feeding the same table you can upload the second file via the table mappings interface
### Step 3 (Migrating data to Database)
  - When you correctly provide the table mappings, an attempt to add the data to the database will kick off.
  - Errors encountered will be displayed. Error free insertions will be successful though you can decide to  cancel the entire migration 
   in case of there is an error encountered.
  - Finally a summary will be generated indicating how many rows were migrated and those that failed and each failed insertion a reason for the failure
   plus an indication of whether it's a database error or just an error in the data.
  - And we are done.
  
