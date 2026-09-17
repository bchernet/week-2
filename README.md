# Week 2 Homework — ISLP Chapter 2

**Name:** Bemnet Chernet  
**Course:** DATA 201: Statistical Methods in Data Science  
**Week:** 2

---

## Exercise 1

### (a)
A more flexible statistical learning method would probably work better because there are a lot of observations and only a few predictors.

### (b)
A less flexible method would probably work better because there are many predictors but only a small number of observations. A flexible method could overfit the data.

### (c)
A more flexible method would probably work better because the relationship is strongly nonlinear.

### (d)
A less flexible method would probably work better because the data has a lot of noise. A flexible method may fit the noise instead of the actual pattern.

---

## Exercise 2

### (a)
This is a **regression** problem because the CEO salary is a quantitative outcome. The goal is **inference** because we want to understand the relationship between salary and the predictors.

- Number of observations: **n = 500**
- Number of predictors: **p = 3**

### (b)
This is a **classification** problem because the outcome is either success or failure. The goal is **prediction** because we want to predict whether a new company will be successful.

- Number of observations: **n = 20**
- Number of predictors: **p = 13**

### (c)
This is a **regression** problem because the percentage change is a quantitative outcome. The goal is **prediction** because we want to predict the percentage change in the USD/Euro exchange rate.

- Number of observations: **n = 52**
- Number of predictors: **p = 3**

---

## Exercise 3

As model flexibility increases:

- **Bias² decreases**
- **Variance increases**
- **Training error decreases**
- **Test error usually decreases at first and then increases**
- **Bayes error stays the same**

A more flexible model usually fits the training data better. However, if it becomes too flexible, it can overfit and perform worse on new data.

---

## Exercise 4

### Classification Examples

1. Predicting whether an email is spam or not spam.
2. Predicting whether a person will be approved or not approved for a loan.
3. Predicting whether a patient has a certain disease.

### Regression Examples

1. Predicting the price of a house.
2. Predicting a student's GPA.
3. Predicting a car's fuel efficiency.

### Clustering Examples

1. Grouping customers based on shopping behavior.
2. Grouping students based on similar characteristics.
3. Grouping cities based on similar data.

---

## Exercise 5

More flexible methods can find complicated relationships in data. However, they can also overfit, especially when there is not enough data.

Less flexible methods are easier to understand and are less likely to overfit, but they may not capture complicated relationships.

A flexible method can be useful when there is a lot of data and the relationship is complex. A less flexible method can be useful when the dataset is smaller or the relationship is simple.

---

## Exercise 6

A **parametric** method assumes a specific form for the relationship between the predictors and the response. The model then estimates the parameters of that relationship.

A **nonparametric** method does not make a strong assumption about the form of the relationship.

One advantage of a parametric method is that it is usually easier to understand and can work well with less data. A disadvantage is that the model may be too simple if the real relationship is different from the assumed form.

---

## Exercise 7

The test observation is:

**X₁ = 0, X₂ = 0, X₃ = 0**

The distances are:

| Observation | Distance | Color |
|---|---:|---|
| 1 | 3 | Red |
| 2 | 2 | Red |
| 3 | √10 ≈ 3.16 | Red |
| 4 | √5 ≈ 2.24 | Green |
| 5 | √2 ≈ 1.41 | Green |
| 6 | √3 ≈ 1.73 | Red |

For **K = 1**, the closest observation is Observation 5, which is **Green**.

For **K = 3**, the three closest observations are Observations 5, 6, and 2. Two are Red and one is Green, so the prediction is **Red**.

If the Bayes decision boundary is highly nonlinear, a small value of K would probably work better because it allows the model to be more flexible.

---

# Exercise 8 — College Data

I used the College dataset and examined the variables, summary statistics, and graphs.

```python
import pandas as pd
import matplotlib.pyplot as plt

college = pd.read_csv("College.csv", index_col=0)

college.head()
college.shape
college.columns
college.describe()

The graphs show differences in tuition, applications, enrollment, and graduation rates among colleges.

---

# Exercise 9 — Auto Data

I loaded the Auto dataset and removed observations with missing values.

Auto = pd.read_csv("Auto.csv", na_values="?")
Auto = Auto.dropna()
After removing the missing observations, there are 392 observations.

The quantitative variables include:

Cylinders
Displacement
Horsepower
Weight
Acceleration
Year

The qualitative variables include:

Origin
Name

Some summary statistics are:

Variable	Mean	Standard Deviation
Cylinders	5.47	1.71
Displacement	194.41	104.64
Horsepower	104.47	38.49
Weight	2977.58	849.40
Acceleration	15.54	2.76
Year	75.98	3.68

I also created scatterplots comparing MPG with horsepower, weight, and displacement.

Auto.plot.scatter(x="horsepower", y="mpg")
plt.show()

Auto.plot.scatter(x="weight", y="mpg")
plt.show()

Auto.plot.scatter(x="displacement", y="mpg")
plt.show()

The graphs show that MPG generally decreases as horsepower, weight, and displacement increase.

Exercise 10 — Boston Data

I loaded the Boston dataset and examined its variables.

from ISLP import load_data

Boston = load_data("Boston")

Boston.shape
Boston.describe()

The dataset contains 506 observations and 13 variables.

Some of the relationships I found were:

RM and MEDV have a positive relationship.
LSTAT and MEDV have a negative relationship.
RM and LSTAT have a negative relationship.
Crime rate is related to several other variables, including RAD, TAX, and LSTAT.

There are 35 towns that border the Charles River.

Boston["chas"].sum()

The median pupil-teacher ratio is 19.05.

Boston["ptratio"].median()

The minimum median home value is 5.0, which represents $5,000 because MEDV is measured in thousands of dollars.

There are 64 suburbs with more than 7 average rooms per dwelling.

(Boston["rm"] > 7).sum()

There are 13 suburbs with more than 8 average rooms per dwelling.

(Boston["rm"] > 8).sum()

Overall, the Boston data shows relationships between housing prices, number of rooms, lower-status population, crime rate, and other characteristics.

Conclusion

This week's homework helped me review statistical learning concepts such as regression, classification, clustering, flexibility, bias and variance, parametric and nonparametric methods, and K-nearest neighbors. I also practiced working with datasets, missing values, categorical variables, and basic data analysis using Python.


### How to put it on GitHub

1. Go to your **DATA 201 GitHub repository**.
2. Click **Add file**.
3. Choose **Create new file**.
4. Name the file:
   **`README.md`**
5. Copy and paste the entire content above.
6. Scroll down and click **Commit changes**.

**Important:** Don't copy the ```markdown at the very beginning or the ``` at the very end.
