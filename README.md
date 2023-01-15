# cap_project :the code for my capstone project
import os
import pandas as pd
import numpy as np 
import seaborn as sns
import matplotlib.pyplot as plt
path = '../input/heart-disease-prediction-using-logistic-regression/framingham.csv'
data = pd.read_csv(path)
data.head()
data.describe() # get statistical summaries for numeric columns
data.isnull().sum() # count the null value in each column
columns_with_null_val = ['education','cigsPerDay','BPMeds','totChol','BMI','heartRate','glucose']

for re in columns_with_null_val: 
    data[re].fillna(data[re].mean(),inplace=True)
    
data.isnull().sum() # Check again the null values
