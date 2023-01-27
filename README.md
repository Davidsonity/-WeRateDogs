# WeRateDogs

![ratedog](https://user-images.githubusercontent.com/96771321/215121953-9e0aadf0-b7ed-4d0a-b379-044287622972.jpg)
> View Notebook @ https://github.com/Davidsonity/WeRateDogs/blob/main/wrangle_act.ipynb

## About Dataset
WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. The data contains was scraped from twitter. For this project, the dataset was provided by Udacity ALX Data Analysis Nanodegree Program.

## Project Steps Overview
Task in this project involves:

- Gathering data

- Assessing data

- Cleaning data

- Storing data

- Analyzing, and visualizing data

- Reporting
> data wrangling efforts \
> data analyses and visualizations


### 1. Gathering Data:
This section require three pieces of dataset to be gathered:

- twitter_archive_enhanced.csv
> This dataset is a csv file downloaded manually from the link given `twitter_archive_enhanced.csv`

- image_predictions.tsv
> This dataset was downloaded using python request library from the url: `image_predictions.tsv`

- tweet_json.txt
> This dataset is a txt file gotten from the supporting material section provided by Udacity `tweet_json.txt`

### 2. Accessing Data:
Each dataset gathered were read individually using python library tool Pandas. This enabled the datasets to be accessed both visually and programmatically.

During the accessment for each dataset, the following issues were observed.

`Quality Issues:`

- 1.) Erroneous datatype : 'tweet_id' in all three tables and 'timestamp' in archived table
**archived table**
- 2.) Retweets are presents: Only original ratings (no retweets) that have images should be considered
- 3.) Missing information (in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_status_user_id, retweeted_status_timestamp)
- 4.) The column 'source' has unnecessary html tags.
- 5.) The column 'name' has inaccurate values starting with lowercase letters : a, an, all, the, mad, not by etc, instead of 'None'
- 6.) The column 'expanded_urls' has null values
- 7.) urls links at the end of the column 'text'
**image_df table**
- 8.) Drop unnecessary columns and give p1 a better names.
`Tidiness issues:`

- 9.) Redundant columns of the same category, ['doggo', 'flooter', 'pupper', 'puppo'] columns, but we only need one 'stage' column
- 10.) "retweet count" and "favorite count" columns are not in the archived
### 3. Cleaning Data:
**FIRST STEP:** I made a copy of three dataframes using pandas function .copy()

- archived_clean = archived.copy()
- image_df_clean = image_df.copy()
- retweet_df_clean = retweet_df.copy()

#### FUTHER STEPS:

##### For archived table
- I converted 'tweet_id' in all three tables from int to string and 'timestamp' to pandas datetime in archived table
- I dropped the rows with values present in in_reply_to_status_id and retweeted_status_id columns
- I dropped the columns (in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_status_user_id, retweeted_status_timestamp)
- I used BeautifulSoup on the 'source' column to get the texts from the tag
- I replaced names starting with lowercase letters with 'None'
- I dropped null values in expanded_urls
- I removed the url link at the end of the each tweet for the column 'text'
##### For image_df table
- I dropped columns (p2, p2_conf, p2_dog, p3, p3_conf, p3_dog) and renamed p1, p1_conf, p1_dog to breed, onfidence and results respectively.
##### For Tidiness issues
- In archived_clean table, I created a new column named 'stage' and catergorise it based on doggo, flooter, pupper, puppo.
- In archived_clean table, I dropped ['doggo', 'flooter', 'pupper', 'puppo'] columns
- I merged retweet_df with archived_df_clean to give merged_df1_clean
- Lastly I merged merged_df1 with image_df_clean

#### 🛠 Issues and solutions

|Issues no	| Solution |
| --------- | -------- |
| 1	| Convert 'tweet_id' in all three tables from int to string and 'timestamp' to pandas datetime in archived table |
| 2	| Drop observations reply and retweet, by deleting the rows with values present in in_reply_to_status_id and retweeted_status_id columns |
| 3	| Drop the columns (in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_status_user_id, retweeted_status_timestamp) |
| 4	| Use BeautifulSoup to get the texts from the tag |
| 5	| Replace names starting with lowercase letters with 'None' |
| 6	| Drop null values in expanded_urls |
| 7	| Removed the url link at the end of the each tweet for the column 'text' |
| 8	| Drop p2, p2_conf, p2_dog, p3, p3_conf, p3_dog and rename p1, p1_conf, p1_dog |
| 9	| Create new column 'stage', catergorise it based on doggo, flooter, pupper, puppo and lastly drop ['doggo', 'flooter', 'pupper', 'puppo'] columns |
| 10 | Merge retweet_df with archived_df |
