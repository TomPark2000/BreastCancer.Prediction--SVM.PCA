# Breast Cancer Prediction with Principal Component Analysis and Support Vector Machines 

## Project Overview
**The primary objective of this project is to create an algorithm to predict whether or not a breast cancer is benign or malignant based off the characteristics of the cell nuclei that are present. There are multiple variables within this data set, so I leveraged Principal Component Analysis and Support Vector Machines to create my algorithm. My algorithm is able to predict whether the cancer is benign or malignant with a 94% overall acccuracy and a 93% F1-score for benign, and 95% score for malignant.** The dataset is the Breast Cancer Wisconsin (Diagnostic) dataset provided by the University of Wisconsin (1995). 

The characteristics of the cell nuclei within the data set include:
- radius (mean of distances from center to points on the perimeter)
- texture (standard deviation of gray-scale values)
- perimeter
- area
- smoothness (local variation in radius lengths)
- compactness (perimeter^2 / area - 1.0)
- concavity (severity of concave portions of the contour)
- concave points (number of concave portions of the contour)
- symmetry
- fractal dimension ("coastline approximation" - 1)



## Libraries Used
numpy, pandas, matplotlib, seaborn, sklearn

## Exploratory Data Analysis
### Plotting Time on Website and Time on App to Yearly Amount Spent:
Since we are trying to determine whether to focus efforts on their mobile or website experience, I plotted "Time on App" and "Time on Website" vs. "Yearly Amount Spent" in order to visualize the correlations. From these two graphs, I can see that Time on App has a higher correlation to Yearly Amount Spent compared to Time on Website.
![](images/LR_eda1.png) ![](images/LR_eda2.png)


### Plotting ALL Relationships:
I wanted to get a snapshot of all the relationships in the entire dataset, so I created a pairplot on the entire dataset. Based off this plot, **the most correlated feature with Yearly Amount Spent is Length of Membership.**

![](images/LR_eda4.png)

I created a linear model plot of the Yearly Amount Spent vs. Length of Membership

![](images/LR_eda5.png)



## Linear Regression Model and Predictions
I created testing and training data, with the x-values being "Avg. Session Length", "Time on App", "Time on Website", and "Length of Membership", and the y-value being "Yearly Amount Spent". I then fit my linear regression model to the training data.


## Evaluation of Model Predictions

The model predicted what the Y values would be for the the test data. I plotted out the Predicted Values and the Actual Values on a scatter plot and from this visualization, it seems that the model did pretty well. For context, a perfectly diagonal line would indicate a perfect model on the test data. 

![](images/LR_pred.png)

For the mathematical evaluation of the model:

Root Mean Squared Error: 8.934

Mean Absolute Error: 7.228

Variance Score = 0.989

The model had a ~9% RMSE and ~99% of the variance is explained by my model, which means that it's a very good fit. This is also supported by the residuals visulization below: 

![](images/LR_resid.png)


## Conclusion and Findings

So, should the company focus their efforts on website development or their mobile app? To answer this question in an effective way, I found the coefficients of my model:

![](images/LR_coeff.png)

To interpret the coefficients, for all other features fixed:
-a 1 unit increase in **Avg. Session Length** is associated with an **increase of 25.98 total dollars spent**.

-a 1 unit increase in **Time on App** is associated with an **increase of 38.59 total dollars spent**.

-a 1 unit increase in **Time on Website** is associated with an **increase of 0.19 total dollars spent**.

-a 1 unit increase in **Length of Membership** is associated with an **increase of 61.27 total dollars spent**.


Based on this, the company should **focus their efforts on their mobile app** because it's highly correlated with the amount of money that the customers spend.
