<H1 ALIGN =CENTER> Ex:1 Introduction to Kaggle and Data preprocessing</H1>

<H3>NAME: Vincy Jovitha V</H3>
<H3>REGISTER NO.: 212223230242</H3>
<H3>DATE:07.03.2025</H3>

## AIM:

To perform Data preprocessing in a data set downloaded from Kaggle

## EQUIPMENTS REQUIRED:
Hardware – PCs
Anaconda – Python 3.7 Installation / Google Colab /Jupiter Notebook

## RELATED THEORETICAL CONCEPT:

**Kaggle :**
Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. Kaggle allows users to find and publish data sets, explore and build models in a web-based data-science environment, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges.

**Data Preprocessing:**

Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. Data Preprocessing is a technique that is used to convert the raw data into a clean data set. In other words, whenever the data is gathered from different sources it is collected in raw format which is not feasible for the analysis.
Data Preprocessing is the process of making data suitable for use while training a machine learning model. The dataset initially provided for training might not be in a ready-to-use state, for e.g. it might not be formatted properly, or may contain missing or null values.Solving all these problems using various methods is called Data Preprocessing, using a properly processed dataset while training will not only make life easier for you but also increase the efficiency and accuracy of your model.

**Need of Data Preprocessing :**

For achieving better results from the applied model in Machine Learning projects the format of the data has to be in a proper manner. Some specified Machine Learning model needs information in a specified format, for example, Random Forest algorithm does not support null values, therefore to execute random forest algorithm null values have to be managed from the original raw data set.
Another aspect is that the data set should be formatted in such a way that more than one Machine Learning and Deep Learning algorithm are executed in one data set, and best out of them is chosen.


## ALGORITHM:
#### STEP 1:
Import Libraries: Load required libraries like pandas, MinMaxScaler, and train_test_split.<BR>
#### STEP 2:
Load Dataset: Read the dataset using pd.read_csv().<BR>
#### STEP 3:
Clean Data: Handle missing values, check for duplicates, and inspect outliers with describe(). Drop unnecessary columns.<BR>
#### STEP 4:
Normalize Data: Use MinMaxScaler to scale feature values (exclude the target column).
<BR>
#### STEP 5:
Prepare Features and Target: Separate input features (X) and target values (y).<BR>
#### STEP 6:
Split Data: Use train_test_split() to divide data into training and testing sets.<BR>

##  PROGRAM:
```
#import libraries
import pandas as pd
import io
from sklearn.preprocessing import StandardScaler
from sklearn.preprocessing import MinMaxScaler
from sklearn.model_selection import train_test_split

#Read the dataset from drive
df=pd.read_csv("Churn_Modelling.csv")
print(df)

#split the dataset
X = df.iloc[:, :-1].values
print(X)
y = df.iloc[:, -1].values
print(y)

# Finding Missing Values
print(df.isnull().sum())

#Check for Duplicates
df.duplicated()

# Check for Outliers using describe()
print("Outliers (Summary Statistics):\n", df.describe(), "\n")

# Drop unnecessary columns (like 'Surname', 'Geography', and 'Gender')
df = df.drop(['Surname', 'Geography', 'Gender'], axis=1)

# Normalize the dataset using MinMaxScaler
scaler = MinMaxScaler()
df_normalized = pd.DataFrame(scaler.fit_transform(df.drop('Exited', axis=1)), columns=df.columns[:-1])
# Normalized dataset
print("Normalized dataset:\n", df_normalized.head(), "\n")

# Define features (X) and target (y)
X = df_normalized.values
y = df['Exited'].values

# Input & Output Values
print("Input Values (Features):\n", X[:5])  # Show first 5 rows of features
print("\nOutput Values (Target):\n", y[:5])  # Show first 5 values of target

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Splitting the data for training & testing
print(f"\nTraining data size: {len(X_train)}")
print(f"Testing data size: {len(X_test)}")
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/905fc6ed-889d-4aab-bf92-ebeed78cf84e)
![image](https://github.com/user-attachments/assets/9fc53c5a-da36-4df7-b33d-455748a9c122)
![image](https://github.com/user-attachments/assets/4dbb48d9-5de5-48b6-a357-bd1b095435a8)
![image](https://github.com/user-attachments/assets/a0b5e174-b4ba-4664-9bb2-aeb1b1d9b44d)
![image](https://github.com/user-attachments/assets/18173d71-1be9-4135-a55d-c606e05eadad)

## RESULT:
Thus, Implementation of Data Preprocessing is done in python  using a data set downloaded from Kaggle.


