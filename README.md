# Titanic-Survival-Conditional-Probability

**Completed by Mangaliso Makhoba.**

**Overview:** This project is using the Titanic Dataset to create a simple statitistical model that will return a conditional survival probabily of a passenger given a condition on a numerical variable from the dataset. 

**Problem Statement:** Build a model that will return a passengers survival chance given a passengers detail as input. 

**Data:** [Titanic Kaggle Challenge](https://www.kaggle.com/c/titanic)

**Deliverables:** Probability

## Topics Covered

1. Statistical Modeling
2. Imputation of Missing values

## Tools Used
1. Scikit-learn
2. Jupyter Notebook

## Installation and Usage

Ensure that the following packages have been installed and imported.

```bash
pip install numpy
pip install pandas
```

#### Jupyter Notebook - to run ipython notebook (.ipynb) project file
Follow instruction on https://docs.anaconda.com/anaconda/install/ to install Anaconda with Jupyter. 

Alternatively:
VS Code can render Jupyter Notebooks

## Notebook Structure
The structure of this notebook is as follows:

 - First, we'll load our data to get a view of the predictor and response variables we will be modeling. 
 - We determine the number of missing values for a specific column
 - We'll then preprocess our data by imputing missing values, mean in numerical features, and mode in categorical feaures. 
 - We then model the survival probabilty of a passenger given their age, class, gender and so on



# Function 1: Missing Values
A function that determines the number of missing entries for a specified column in the dataset. The function should return an `int` that corresponds to the number of missing entries in the specified column.

_**Function Specifications:**_
* Should take a pandas `DataFrame` and a `column_name` as input and return a `int` as output.
* The `int` should be the number of missing entries in the column.
* Should be generalised to be able to work on _**ANY**_ dataframe.


_**Expected Outputs:**_
```python
total_missing(df,'Age') == 177
total_missing(df,'Survived') == 0
```



# Function 2: Imputation

Write a function that takes in as input a dataframe and a column name, and returns the `mean` for numerical columns and the `mode` for non-numerical columns.

_**Function Specifications:**_
* The function should take two inputs: `(df, column_name)`, where `df` is a pandas `DataFrame`, `column_name` is a `str`.
* If the `column_name` does not exist in `df`, raise a `ValueError`.
* Should return as output the `mean` if the specified column is numerical and return a list of the `mode(s)` otherwise.
* The mean should be rounded to 2 decimal places.
* **If there is more than one `mode` for a given non-numerical column, the fuction should return a list of all modes**.

_**Expected Outputs:**_
```python
calc_mean_mode(df, 'Age') == 29.7
calc_mean_mode(df, 'Embarked') == ['S']
```


# Function 3: Model
We ultimately want to predict the survival chances of the passengers in the testing set. We can start by building a simple model using the data we already have by using _conditional probability_ ! Write a function that returns the survival probability of a passenger, given a condition on a **numerical variable** from the dataset. The condition will consist of a `column_name`, a `value` and a `boolean_operator`. Possible boolean operators include `"<"`,`">"`, or `"=="`. For example, `column_name = "Age"`, `boolean_operator = ">"`, and `value = 40` together form the condition `Age > 40`.

_**Function specifications:**_
* The function should make use of the `df_clean` `DataFrame` loaded earlier in this notebook.
* It should take a numerical `column_name` string, a `boolean_operator` string, and a `value` of type string as input. 
* It should return a survival likelihood as a number between 0 and 1, rounded to 2 decimal places. 
* Assume that `column_name` exists in `df_clean`.

_**Expected Outputs:**_
```python
survival_likelihood(df_clean,"Pclass","==","3") == 0.24
survival_likelihood(df_clean,"Age","<","15") == 0.58
```

## Conclusion
Finding an appropriate strategy to impute missing values is very important to increasing the accuracy of the model you are building. 

## Contributing Authors
**Authors:** Mangaliso Makhoba, Explore Data Science Academy

**Contact:** makhoba808@gmail.com

## Project Continuity
This is project is complete

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change. 

## License
[MIT](https://choosealicense.com/licenses/mit/)
