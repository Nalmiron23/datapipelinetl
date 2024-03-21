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
