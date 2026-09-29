This project demonstrates the fundamental data preparation and exploratory data analysis workflow used in a data science project.

The main objectives are:

Acquire a publicly available dataset

Inspect the dataset structure and quality

Handle missing values

Remove duplicate records

Correct data types

Perform exploratory data analysis (EDA)

Create meaningful visualizations

Identify important patterns and insights

Export the cleaned dataset

📊 Dataset

Titanic Passenger Dataset

The Titanic dataset contains information about passengers aboard the RMS Titanic, including passenger class, sex, age, fare, family information, embarkation details, and survival status.

Dataset Source:

https://github.com/mwaskom/seaborn-data/blob/master/titanic.csv

Dataset Size

Rows: 891

🛠️ Technologies Used

Python

Pandas

NumPy

Matplotlib

Seaborn

Jupyter Notebook


 Project Workflow

Data Acquisition
       ↓
Initial Data Inspection
       ↓
Missing Value Analysis
       ↓
Data Cleaning
       ↓
Data Type Validation
       ↓
Duplicate Handling
       ↓
Exploratory Data Analysis
       ↓
Data Visualization
       ↓
Insights Generation
       ↓
Cleaned Dataset

🧹 Data Cleaning

The following preprocessing steps were performed:

1. Categorical Data Standardization

Categorical columns such as sex and embarked were standardized by removing unnecessary whitespace and ensuring consistent string representation.

2. Numeric Data Type Correction

The following columns were converted to appropriate numeric types:

survived

pclass

age

sibsp

parch

fare

3. Missing Age Values

The age column contained missing values.

Instead of using one global value, missing ages were filled using the median age calculated within groups based on:

Passenger class (pclass)

Sex (sex)

This preserves some of the differences between passenger groups.

4. Missing Embarked Values

Only a small number of embarked values were missing, so the mode was used for imputation.

5. Deck Column

The deck column contained a very high proportion of missing values. Rather than making unsupported assumptions about missing deck information, the column was removed for this Week 1 analysis.

6. Duplicate Records

Exact duplicate rows were checked and removed from the dataset.

📈 Exploratory Data Analysis

The project includes the following visualizations:

1. Missing Values

A heatmap was created to visualize the location of missing values in the original dataset.

2. Survival Rate by Sex

The survival rate was compared between male and female passengers.

3. Survival Rate by Passenger Class

Survival rates were compared across first, second, and third passenger classes.

4. Age Distribution

A histogram with KDE was used to understand the distribution of passenger ages after imputation.

5. Correlation Matrix

A correlation heatmap was created to examine relationships between numerical variables such as:

Survival

Passenger class

Age

Siblings/spouses

Parents/children

Fare

🔍 Key Insights

The exploratory analysis produced several observations:

The dataset contains 891 passenger records.

Passenger survival was not evenly distributed across the dataset.

Survival rates differed considerably between male and female passengers.

Passenger class showed a noticeable relationship with survival.

Age has a broad distribution across passengers.

The deck variable has substantial missing information and requires careful feature engineering if used in future analysis.

Correlation analysis helps identify relationships between numerical variables but does not establish causation.