# Maji Ndogo's Agriculture Integrated Project
Welcome to the repository for the Maji Ndogo's Agriculture Integrated Project! This project is divided into three main parts, each focusing on different aspects of data analysis using Python and Pandas.

## Table of Contents

- Project Overview

- Part 1: Data Import and Cleaning

- Part 2: Exploratory Data Analysis (EDA) and Visualization

- Part 3: Data Validation and Hypothesis Testing

- Setup and Installation

- License



## Project Overview

Maji Ndogo's Agriculture Integrated Project is a comprehensive data analysis project aimed at understanding and improving agricultural practices in the Maji Ndogo region. The project involves cleaning, analyzing, and validating agricultural data using Python.

### Part 1: Data Import and Cleaning
#### Introduction
The purpose of this part is to import the dataset from an SQLite database, clean it, and prepare it for analysis.

Libraries Used:
- pandas: For data manipulation and analysis.
- sqlite3: For connecting to and importing data from the SQLite database.
Content
Data Import
The dataset is imported from an SQLite database into a Pandas DataFrame.

here are some functions:

    def load_data(db_path, query):
    conn = sqlite3.connect(db_path)
    df = pd.read_sql_query(query, conn)
    conn.close()
    return df
#### Data Cleaning

Steps taken to clean the data include handling missing values, correcting data types, and removing duplicates.


    def clean_data(df):
      # Handle missing values
      df = df.dropna()
    
      # Correct data types
      df['column_name'] = df['column_name'].astype('desired_type')
    
      # Remove duplicates
      df = df.drop_duplicates()
    
      return df

#### File

1-Maji_Ndogo's_Agriculture_Integrated_Project_P1_Submission.ipynb



### Part 2: Exploratory Data Analysis (EDA) and Visualization

#### Introduction

The purpose of this part is to explore the dataset visually and uncover insights.

###### Libraries Used:

- pandas: For data manipulation and analysis.

- seaborn: For creating visualizations.

- matplotlib: For creating visualizations.

- numpy: For numerical operations.

##### Content
Data Exploration

Exploring the dataset to identify patterns and correlations between variables.

    def explore_data(df):
      print(df.describe())
      print(df.info())
      print(df.corr())
Data Visualization

Using Seaborn and other tools to create visualizations.

    import seaborn as sns
    import matplotlib.pyplot as plt

    def visualize_data(df):
      sns.pairplot(df)
      plt.show()
    
      sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
      plt.show()
Data Validation

Validating the dataset using weather data from nearby stations.
  
    def validate_data(df, weather_df):
        merged_df = df.merge(weather_df, on='date')
        return merged_df
#### File

2-Maji_Ndogo's_Agriculture_Integrated_Project_P2_Submission.ipynb


### Part 3: Data Validation and Hypothesis Testing

##### Introduction

The objective of this part is to validate the dataset through hypothesis testing.

###### Libraries Used

- pandas: For data manipulation and analysis.

- scipy: For statistical hypothesis testing.

- numpy: For numerical operations.

###### Content

- Null Hypothesis

Define the null hypothesis and its significance in the context of the project.

Data Preparation

Preparing the data for hypothesis testing, including importing and cleaning.

    def prepare_data(file_path):
        df = pd.read_csv(file_path)
        df = clean_data(df)
        return df

- Hypothesis Testing

Performing hypothesis testing, including the calculation of relevant statistics and interpretation of results.

    from scipy import stats
    
    def hypothesis_testing(df, column1, column2):
        t_stat, p_val = stats.ttest_ind(df[column1], df[column2])
        return t_stat, p_val
##### File
3-Maji_Ndogo's_Agriculture_Integrated_Project_P3_Submission.ipynb

## Setup and Installation

### Instructions to Run the Project:

#### Prerequisites
- Ensure you have Python 3.7 or higher installed.
- Install SQLite if it's not already installed on your system.
- It is recommended to use a virtual environment to manage dependencies.

#### Step-by-Step Guide

1. **Clone the Repository**
    ```sh
    git clone https://github.com/Youssef-Mohamed1/African-Agricultural-Data-Cleaning-And-Testing-Project.git
    cd maji-ndogo-agriculture-project
    ```

2. **Set Up a Virtual Environment**
    ```sh
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. **Install Dependencies**
    ```sh
    pip install -r requirements.txt
    ```

4. **Run Data Ingestion**
    - This step involves importing data from the SQLite database and processing it.
    - You can run the `data_ingestion.py` script directly:
      ```sh
      python data_ingestion.py
      ```

5. **Process Field Data**
    - Run the `field_data_processor.py` script to clean and prepare field data:
      ```sh
      python field_data_processor.py
      ```

6. **Process Weather Data**
    - Run the `weather_data_processor.py` script to fetch and validate weather data:
      ```sh
      python weather_data_processor.py
      ```

7. **Run Jupyter Notebooks for Detailed Analysis**
    - If you prefer to run the analysis interactively, you can use Jupyter notebooks.
    - Start Jupyter Notebook:
      ```sh
      jupyter notebook
      ```
    - Open and run the following notebooks in order:
      - `FieldDataProcessor.ipynb`
      - `Maji_Ndogo's_Agriculture_Integrated_Project_P1_Submission.ipynb`
      - `Maji_Ndogo's_Agriculture_Integrated_Project_P2_Submission.ipynb`
      - `Maji_Ndogo's_Agriculture_Integrated_Project_P3_Submission.ipynb`
      - `data_ingestion.ipynb`
      - `weather_data_processor.ipynb`

#### Project Structure
- `__pycache__`: Directory for Python bytecode files.
- `FieldDataProcessor.ipynb`: Notebook for processing field data.
- `Maji_Ndogo's_Agriculture_Integrated_Project_P1_Submission.ipynb`: Notebook for Part 1 of the project.
- `Maji_Ndogo's_Agriculture_Integrated_Project_P2_Submission.ipynb`: Notebook for Part 2 of the project.
- `Maji_Ndogo's_Agriculture_Integrated_Project_P3_Submission.ipynb`: Notebook for Part 3 of the project.
- `Maji_Ndogo_farm_survey_small.db`: SQLite database containing raw data.
- `README.md`: This file, providing instructions and documentation.
- `data_ingestion.ipynb`: Notebook for data ingestion processes.
- `data_ingestion.py`: Script for data ingestion.
- `field_data_processor.py`: Script for processing field data.
- `weather_data_processor.ipynb`: Notebook for processing weather data.
- `weather_data_processor.py`: Script for processing weather data.

#### Notes
- Ensure the SQLite database file `Maji_Ndogo_farm_survey_small.db` is in the root directory.
- The project heavily relies on data processing, so ensure the data is correctly ingested and processed before running the analysis notebooks.

By following these instructions, you should be able to set up and run the project smoothly. If you encounter any issues, please check the error messages and verify that all dependencies are correctly installed.

## License and Copyright

### License
This project is licensed under the MIT License. You are free to use, modify, and distribute this software in accordance with the license terms.

### Copyright
&copy; 2024 [Youssef Abdelmotteleb]. All rights reserved.

### Acknowledgements
This project was developed as part of the Explore AI Academy curriculum. Some of the advanced functions and code components were pre-written and provided by Explore AI Academy for educational purposes.

### Data Attribution
The data used in this project is sourced from Explore AI Academy and is intended solely for educational and non-commercial use. Any use of this data beyond the scope of this project should be done in accordance with the terms provided by Explore AI Academy.

### Thank You
Thank you to everyone who has taken the time to go through this project. Your interest and feedback are greatly appreciated.

