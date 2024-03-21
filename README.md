# Data Pipeline ETL

***Getting Started with Data Pipelines for ETL***

---------

***Extracting Data*** <br>
In this code-along, I'll focus on extracting data from flat-files. A flat file might be something like a .csv or a .json file. The two files that I'll be extracting data from are the apps_data.csv and the review_data.csv file. To do this, I'll used pandas. 

After importing pandas, read the apps_data.csv DataFrame into memory. Print the head of the DataFrame.
Similar to before, read in the DataFrame stored in the review_data.csv file. Take a look at the first few rows of this DataFrame.
Print the column names, shape, and data types of the apps DataFrame.

----------
***Transforming Data*** <br>
I am interested here in working with the apps and their corresponding reviews in the"FOOD_AND_DRINK" category. I'd like to do the following:

Define a function with name transform. This function will have five parameters; apps, review, category, min_rating, and min_reviews.
Drop duplicates from both DataFrames.
For each of the apps in the desired category, find the number of positive reviews, and filter the columns.
Join this back to the apps dataset, only keeping the following columns:
App
Rating
Reviews
Installs
Sentiment_Polarity
Filter out all records that don't have at least the min_rating, and more than the min_reviews.
Order by the rating and number of installs, both in descending order.
Call the function for the "FOOD_AND_DRINK" category, with a minimum average rating of 4 stars, and at least 1000 reviews.

----------
***Loading Data***<br>
Next, I'd like to load the transformed dataset into a SQL database. i'll be using pandas along with sqlite to do just that!

After importing sqlite3, create a function with name load. The function will have four parameters; dataframe, database_name, table_name.
Connect to the database using the connect() function.
Write the DataFrame to the provided table name. Replace the table if it exists, and do not include the index.
Now, we'll validate that the data was loaded correctly. Use the read_sql() function to return the DataFrame that was just loaded.
Assert that the number of rows and columns match in the original and loaded DataFrame.
Return the DataFrame read from the sqlite database.
Call the function for the top_apps_data DataFrame, for the "market_research" database and the top_apps table.

----------
