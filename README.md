# Module_8_Movies_ETL

# Project Scope
  This project is divided into 4 sections. In summary, we have created an autimated pipeline that takes in new data, performs some
  appropiate transformations and clean the data and loads the data into exsisting tables.
  As input, we have 3 files:
  - Wikipedia data
  - Kaggle metadata
  - MovieLens rating data
  These datas are used to perform some ETL processes, and adding the data to a PostgreSQL database
  
# Resources
  - Data sources: Wikipedia-movies.json, movies_metadata.csv, ratings.csv
  - Software: PostgreSQL v11.12, pgAdmin 4, Python 3.7.6, Visual Studio Code version 1.58
  - web application: Jupyter Notebook 
  

# Analysis
  Analysis are made in form of following instructions to writing the codes for the ETL process. The codes and comments can be found in
  the attached 4 ipynb files.
  
  - The purpose and outcome of the first file is to read in and convert the files to data frames using defnition functions
  
  - The purpose and the outcome of the second file is to clean the movie data for some preferences like filtering ou TV shows, and create 
    a clean wiki_movies_df DataFrame. The columns to be cleaned are written as comments in the code in file "ETL_clean_wiki_movies.ipynb".
    This process was done using  by using definition functions, regular expressions, and lambda functions. 
  
  - The purpose of the thrird file is to clean the Kaggle metadata and MovieLens rating data, following similar steps as for the clean movie data.
    and convert the transformed data into separate DataFrames. After this step, we merge the Kaggle metadata DataFrame with the Wikipedia movies
    DataFrame to create the movies_df DataFrame. Final step is to merge the MovieLens rating data Dataframe with the movies_df DataFrame to create
    movies_with_ratings_df.
    
    
    
  - For deliverable 4, we add codes at the end to create a connection to the PostgreSQL database, and adding the movies_df DataFrame and the 
    and import the ratings data, while printing out the elapsed time to import each row.
    We need to make sure that we add a code so that the data from the movies_df DataFrame replaces the current data in the movies table in the SQL database.
    For this we use this code:
        movies_df.to_sql(name='movies', con=engine, if_exists='replace')

  
# Results
  The results are the actual codes that are submitted in this repository with some screen grabs.
