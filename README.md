## Data Analysis of Wine Quality Factors Using Linear Regression
- Kim Damalas, 24 Jan 2021; seattle-401pyn2
- From Kaggle [wine quality factors](https://www.kaggle.com/uciml/red-wine-quality-cortez-et-al-2009)


Submission pull request: https://github.com/kimmyd70/linear-regression/pull/1

## Description
___________

Taking a tour into Data Science to learn a bit more about the field and tools used in this space
____________
## Feature Tasks and Requirements
___________

1. Load the data you receive into a Pandas DataFrame.
2. Show the first five rows of the data set.
3. Show the description and the info of the data set.
4. Ensure that any date columns have been cast into a datetime object in your DataFrame.
5. Using a regression model, split your data into train and test data.
6. Fit your training split to the regression model.
7. Show your regression model’s score.
8. Draw at least three conclusions from your regression model.
Questions to draw conclusions:  
- How does residual sugar affect % alcohol of wine?
- How does overall fixed acidity correlate to citric acid ("freshness") in this wine variant?
- How does the quantity of volatile acid (vinegar or nail polish smells/taste) correlate to sensory rating (1-10) of quality of this wine variant?
______________

## Configuration and Technologies
__________

The user must have Python and all associated dependencies installed.  The project is run inline using a Jupyter notebook
___________
## Changes
__________

23 Jan: files set up; grid coded; first PR
24 Jan: coding finished; notebook cleaned up and turned in on Canvas
___________

## Testing
________

Not required for this lab

## Dataset
_________

This datasets is related to red variants of the Portuguese "Vinho Verde" wine. For more details, consult the reference [Cortez et al., 2009].

Input variables (based on physicochemical tests):
   1 - fixed acidity (tartaric acid - g / dm^3)
   2 - volatile acidity (acetic acid - g / dm^3)
   3 - citric acid (g / dm^3)
   4 - residual sugar (g / dm^3)
   5 - chlorides (sodium chloride - g / dm^3
   6 - free sulfur dioxide (mg / dm^3)
   7 - total sulfur dioxide (mg / dm^3)
   8 - density (g / cm^3)
   9 - pH
   10 - sulphates (potassium sulphate - g / dm3)
   11 - alcohol (% by volume)
   Output variable (based on sensory data): 
   12 - quality (score between 0 and 10)

   ** g/dm^3 is grams per volume of a liquid solvent/solution

1599 total entries


Citation:
P. Cortez, A. Cerdeira, F. Almeida, T. Matos and J. Reis. Modeling wine preferences by data mining from physicochemical properties. In Decision Support Systems, Elsevier, 47(4):547-553, 2009.

_________

## Dataset Normalization (kind of)

__________
1451 entries after:

```
df = pd.DataFrame(np.random.randn(100, 3))

from scipy import stats
df[(np.abs(stats.zscore(df)) < 3).all(axis=1)]

```

description of process to detect and exclude outliers (3) std from [Stack Overflow](https://stackoverflow.com/questions/23199796/detect-and-exclude-outliers-in-pandas-data-frame):

- For each column, first it computes the Z-score of each value in the column, relative to the column mean and standard deviation.
- Then is takes the absolute of Z-score because the direction does not matter, only if it is below the threshold.
- all(axis=1) ensures that for each row, all column satisfy the constraint.
- Finally, result of this condition is used to index the dataframe.
