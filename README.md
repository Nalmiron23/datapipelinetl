# Data Pipeline ETL

***Getting Started with Data Pipelines for ETL***

---------

***Extracting Data*** <br>
In this code-along, I'll focus on extracting data from flat-files. A flat file might be something like a .csv or a .json file. The two files that I'll be extracting data from are the apps_data.csv and the review_data.csv file. To do this, I'll used pandas. 

After importing pandas, read the apps_data.csv DataFrame into memory. Print the head of the DataFrame. <br>
Similar to before, read in the DataFrame stored in the review_data.csv file. Take a look at the first few rows of this DataFrame. <br>
Print the column names, shape, and data types of the apps DataFrame. <br>

----------
***Transforming Data*** <br>
I am interested here in working with the apps and their corresponding reviews in the"FOOD_AND_DRINK" category. I'd like to do the following:

Define a function with name transform. This function will have five parameters; apps, review, category, min_rating, and min_reviews.<br>
Drop duplicates from both DataFrames.<br>
For each of the apps in the desired category, find the number of positive reviews, and filter the columns.<br>
Join this back to the apps dataset, only keeping the following columns:
App <br>
Rating <br>
Reviews <br>
Installs <br>
Sentiment_Polarity <br>
Filter out all records that don't have at least the min_rating, and more than the min_reviews. <br>
Order by the rating and number of installs, both in descending order.<br>
Call the function for the "FOOD_AND_DRINK" category, with a minimum average rating of 4 stars, and at least 1000 reviews.

----------
***Loading Data***<br>
Next, I'd like to load the transformed dataset into a SQL database. i'll be using pandas along with sqlite to do just that!

After importing sqlite3, create a function with name load. The function will have four parameters; dataframe, database_name, table_name.<br>
Connect to the database using the connect() function.<br>
Write the DataFrame to the provided table name. Replace the table if it exists, and do not include the index.<br>
Now, we'll validate that the data was loaded correctly. Use the read_sql() function to return the DataFrame that was just loaded.<br>
Assert that the number of rows and columns match in the original and loaded DataFrame.<br>
Return the DataFrame read from the sqlite database.<br>
Call the function for the top_apps_data DataFrame, for the "market_research" database and the top_apps table.<br>

----------

***Running the Pipeline***<br>
Now that functions have been defined and tested, I'll run this pipeline end-to-end!

For verbosity, import pandas and sqlite3.<br>
Extract data from the apps_data.csv and review_data.csv functions.<br>
Transform the data by passing in the following:
category="FOOD_AND_DRINK"<br>
min_rating=4.0<br>
min_reviews=1000<br>
Load the transformed DataFrame to the top_apps table in the market_research database.<br>
Checking out the output!

----------
