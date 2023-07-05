# WeRateDogs Twitter Data Wrangling and Analysis

![ratedog](https://user-images.githubusercontent.com/96771321/215121953-9e0aadf0-b7ed-4d0a-b379-044287622972.jpg)

## Project Overview

This project focuses on wrangling and analyzing Twitter data. The data is obtained from the WeRateDogs Twitter account and consists of various attributes such as tweet text, ratings, retweet count, favorite count, and dog stage. The goal is to gather data from different sources, assess its quality and tidiness, clean the data, and perform exploratory analysis to gain insights into the WeRateDogs tweets.

## Project Structure

The project directory is structured as follows:

```
├── wrangle_act.ipynb
├── wrangle_report.ipynb
├── act_report.ipynb
├── twitter_archive_master.csv
├── twitter-archive-enhanced.csv
└── README.md
```

- `wrangle_act.ipynb`: This Jupyter Notebook contains the code for data wrangling, which includes data gathering, assessment, cleaning, and storing the cleaned data.
- `wrangle_report.ipynb`: This Jupyter Notebook provides a detailed report on the data wrangling process, including the steps taken to gather, assess, and clean the data.
- `act_report.ipynb`: This Jupyter Notebook contains a report on the data analysis performed on the cleaned dataset, along with insights and visualizations.
- `twitter_archive_master.csv`: This CSV file contains the cleaned and processed data after the data wrangling phase. It serves as the final dataset used for analysis and visualizations.
- `twitter-archive-enhanced.csv`: This CSV file is the original data provided by Udacity. It is the starting point of the data wrangling process and is referenced during the project for comparison and data assessment purposes.
- `README.md`: This file provides an overview of the project, its structure, and instructions for running the code.

## Dataset

The dataset used in this project is the WeRateDogs Twitter data. It consists of various attributes, including tweet ID, timestamp, text, dog ratings, dog stage (e.g., doggo, floofer, pupper, puppo), retweet count, and favorite count. The dataset is originally provided in the `twitter-archive-enhanced.csv` file.

## Data Wrangling

The data wrangling process involves several steps, including data gathering, data assessment, and data cleaning. The `wrangle_act.ipynb` notebook contains the code for each of these steps.

1. Data Gathering: The data is gathered from three different sources:
   - The `twitter-archive-enhanced.csv` file provided by Udacity
   - The `image_predictions.tsv` file downloaded programmatically using the Python Requests library
   - The `tweet_json.txt` file obtained from the supporting material section provided by Udacity

2. Data Assessment: Each dataset is assessed visually and programmatically to identify quality and tidiness issues. Issues such as missing data, incorrect data types, duplicate data, and inconsistencies are documented.

3. Data Cleaning: The identified issues are addressed by cleaning the data. This involves operations such as fixing data types, removing duplicates, handling missing values, and resolving inconsistencies.

## Data Analysis

After the data is cleaned and stored in the `twitter_archive_master.csv` file, exploratory data analysis is performed in the `act_report.ipynb`

 notebook. The cleaned data is analyzed to gain insights and answer questions about the WeRateDogs Twitter account. The analysis includes descriptive statistics, visualizations, and correlation analysis.

## Results

The analysis of the WeRateDogs Twitter data provides the following insights:

- Distribution of numeric columns: The distributions of retweet count and favorite count are skewed, with the majority of counts falling within specific ranges.
- Correlations between numerical columns: There is a strong positive correlation between retweet count and favorite count, indicating that tweets with higher retweet counts tend to have higher favorite counts.
- Twitter source most used by #WeRateDogs followers: The analysis reveals that the majority of followers tweet from an iPhone.

For more details, refer to the `act_report.ipynb` notebook.

## Dependencies

The following dependencies are required to run the project:

- Python (version 3.x)
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn

Ensure that these dependencies are installed in your Python environment before running the code.

## Usage

To replicate the project's results, follow these steps:

1. Clone the project repository to your local machine.
2. Ensure that the required dependencies are installed in your Python environment.
3. Open and run the `wrangle_act.ipynb` notebook to perform the data wrangling process. Make sure the `twitter-archive-enhanced.csv` file is present in the project directory.
4. Open and run the `act_report.ipynb` notebook to perform the data analysis. Ensure that the `twitter_archive_master.csv` file is present in the project directory.

## File Descriptions

- `wrangle_act.ipynb`: Jupyter Notebook containing the code for data wrangling.
- `wrangle_report.ipynb`: Jupyter Notebook providing a detailed report on the data wrangling process.
- `act_report.ipynb`: Jupyter Notebook containing the report on the data analysis.
- `twitter_archive_master.csv`: Cleaned and processed dataset after data wrangling.
- `twitter-archive-enhanced.csv`: Original dataset provided by Udacity.
- `README.md`: Project overview, instructions, and information.

## License

This project is licensed under the [MIT License](LICENSE).
