# Movies-ETL
## Background
The delivery of the dataset has been greatly appreciated by Amazing Prime as a result would like us to implement a code to receive updates daily. Assisting Britta, we created an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. Refactoring the code from this module proved necessary and the creation of one function that takes in the three files, Wikipedia data, Kaggle metadata, and the MovieLens, rating data and performs the ETL process by adding the data to a PostgreSQL database.
## Overview of Project
Wikipedia holds up its’ reputation on maintaining an enormous amount of information, including budgets and box office returns, cast and crew, production, and distribution, and so much more. Previously, Britta's coworkers created a script to go through a list of movies on Wikipedia from 1990 to 2018 and extract the data from the sidebar into a JSON. Unfortunately, her coworker can't find the script anymore and just has the JSON file. We'll need to load in the JSON file into a Pandas DataFrame.
## Resources:
•	Products developed: ETL Deliverable 1, ETL Deliverable 2 and ETL Deliverable 3

•	Data Tools: Jupyter Notebook, PostgreSQL, pgAdmin

•	Software: pgAdmin 4.26, Python 3.8.3, Visual Studio Code 1.50.0, Flask Version 1.0.2

## Procedures  
###  Outline of Results
####  Deliverable 1
1.	The function converts the Wikipedia JSON file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file.
2.	An ETL function is written to read in the three data files. 
3.	The function converts the Kaggle metadata file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file.
<p align="center">
   <img width="800" height="600" src="https://github.com/jacquie0583/Movies-ETL/blob/main/Resource/D%202.png">
</p>  

4.	The function converts the MovieLens ratings data file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file.  Check the wiki_movies_df DataFrame:
<p align="center">
   <img width="800" height="400" src="https://github.com/jacquie0583/Movies-ETL/blob/main/Resource/D1%20Wiki%20DF.png">
</p> 

####  Deliverable 2

1.	The TV shows are filtered out, and the wiki_movies_df DataFrame is created
2.	 A try-except block is used to catch errors while extracting the IMDb IDs with a regular expression and dropping duplicate IDs.
<p align="center">
   <img width="800" height="600" src="https://github.com/jacquie0583/Movies-ETL/blob/main/Resource/D7.png">
</p>  

3.	The extraction and transformation of the Wikipedia data in the ETL function does the following:
<p align="center">
 <img width="800" height="600" src="https://github.com/jacquie0583/Movies-ETL/blob/main/Resource/D%204.png">
</p>  

4.	The cleaned Wikipedia data is converted to a Pandas DataFrame, and the DataFrame is displayed in the ETL_clean_wiki_movies.ipynb file.
<p align="center">
   <img width="800" height="400" src="https://github.com/jacquie0583/Movies-ETL/blob/main/Resource/D1%20Wiki%20DF.png">
</p>  

####  Deliverable 3
1.	The extraction and transformation of the Kaggle metadata using the ETL function.
2.	The extraction and transformation of the MovieLens ratings data using the ETL function. Transform and merge the ratings DataFrame:

<p align="center">
   <img width="800" height="400" src="https://github.com/jacquie0583/Movies-ETL/blob/main/Resource/D%205.png">
</p> 

3.The movies_with_ratings_df and the movies_df DataFrames are displayed in the ETL_clean_kaggle_data.ipynb file as well as below:

<p align="center">
   <img width="800" height="400" src="https://github.com/jacquie0583/Movies-ETL/blob/main/Resource/D%208.png">
</p> 


#### Deliverable 4
1.	The data from the movies_df DataFrame replaces the current data in the movies table in the SQL database, as determined by the movies_query.png.
2.	The data from the MovieLens rating CSV file is added to the ratings table in the SQL database, as determined by the ratings_query.png.

<p align="center">
   <img width="800" height="400" src="https://github.com/jacquie0583/Movies-ETL/blob/main/Resource/ratings_query.png">
</p> 

3.The elapsed time to add the data to the database is displayed in the ETL_create_database.ipynb file.  The elapsed time:
<p align="center">
   <img width="800" height="500" src="https://github.com/jacquie0583/Movies-ETL/blob/main/Resource/processing%20on%20postgress.png">
</p> 
