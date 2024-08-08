# Predicting A Country's Olympic Medal Count

In this project, we will simply try to predict the number of medals a country will win based on mainly 2 features :-
1. Number of athletes that are competing in the Olympics
2. Number of medals the country has won in the previous Olympics

We will be using a linear regression model to predict the target value.


## Notes :-

### 1. Dataset
In our dataset, we have 11 columns :-

1. **team** - Abbreviation of the country into 3 Capital Letters 
2. **country** - Country Name
3. **year** - Year
4. **events** - Number of events that country participated in that olympics
5. **athletes** - Number of athletes from that country
6. **age** - Average age of all the athelets from that country
7. **height** - Average height
8. **weight** - Average weight
9. **medals** - Number of medals the country won during that year's olympics
10. **prev_medals** - Number of medals the country won in the previous olympics
11. **prev_3_medals** - Average of the medals won by the country in the last 3 olympics

### 2. Re-shaping our data
To train our model, we will only use ['team', 'year', 'athletes', 'age', 'prev_medals', 'medals'] column and will drop all the other columns.

### 3. Finding Correlation
To find correlation between **non-categorical** values, we use the `.corr()` function. It will return a matrix with correlation of every feature with every other feature.

Since we only need to find correlation of *medals* feature with other feature, we index the metrics with `["medals"]` to only get that column.

We have also dropped the *team* column since it's a categorical data and Pandas can't find correlation between categorical features.

### 4. Plotting Graphs
To visualize our data, we have used 2 types of graphs :-
1. `sns.lmplot()`
    It stands for Linear Model plot. It is basically used plot 2 variables kinda in the form of scatter plot.
2. `df.plot.hist()`
    It is used to plot histogram (basically to visualize the frequency)

### 5. Splitting the data
Splitting the data such that the training set consists of data before 2012 and the test set consists of data from and after 2012 is a common approach known as time-based splitting. It prepares the model for future predictions by ensuring it only learns from past data.

### 6. Model Training
Once we have splitted our data, we will train our model using `LinearRegression()` class.

To train our model, we will be using only 2 features on our feature DataFrame, ['athletes' and 'prev_medal'].

### 7. Prediction Cleaning
After predicting the target (which in the form of Numpy arrays), we will add a new column to our original DataFrame, **prediction**. 

After that, we will do some cleaning like replacing the negative number of medals with 0 and then rounding off the number of medals.

### 8. Evaluating Our Model
After this, we evaluate our model by finding it's *Mean Absolute Error*. To find the *MAE*, we use the function `mean_absolute_error()` that we imported from `sklearn.metrics`.

<br><br>

> This project was a complete walkthrough of this [tutorial](https://youtu.be/Hr06nSA-qww?si=sHgYNu0jt_xOKKJv) by Dataquest.

-------
