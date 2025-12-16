# Diamond Price Prediction

## Problem Statement
- This dataset contains ~54,000 rows of different diamonds and their properties, such as depth, carat, width, cut, color, etc. 

- The purpose of this analysis is to train a regression model to accurately predict the price of the diamond based on the different characteristics. 

## Data Dictionary

| Column Name | Description |
|-------------|-------------|
| price (target)     | Price in US Dollars |
| carat     | weight of the diamond |
| cut         | quality of the cut (FFair, Good, Very Good, Premium, Ideal)         |
| color | diamond color from J (worst), to D (best) |
| clarity | how clear the diamond is  (I1 (worst), SI2, SI1, VS2, VS1, VVS2, VVS1, IF (best)) |
| x | length in mm |
| y | width in mm |
| z | length in mm |
| depth | total depth percentage|
| table | with of the top of the diamond relative to the widest point |

## Executive Summary

### Data Cleaning Steps
This dataset did not include any missing values, nor any worrisome outliers. However, this data did include duplicates, which were dropped. 

### Key Visualizations

#### Visualization 1: [Correlation between Carat and Price Grouped by Cut]
This scatterplot shows the relationship between carat and price, and the colors group it by the type of cut. We can see that carat and price are strongly related, but the distribution of different cuts do not seem to be as affected by price, as the groups spread out all over the scatterplot.

![Visualization 1](./images/carat_price_cut.png)

#### Visualization 2: [Distribution of Price, Grouped by Clarity]
The below kdeplot shows the distribuiton of the price by the clarity of the diamond.

At first glance, it appears that most of the diamonds are of the clarity VS2, but upon closer inspection, we see a smaller, wide peak for SI1, showing that this clarity is the most common. VS2 is only more common among the lower prices (0-~4000). We also see that the clarity I1 has the lowest probability, having a very small peak and a broad width.
![Visualization 2](./images/price_kde.png)

#### Visualization 3: [Average Price by Cut and Color]
The below heatmap shows the average price for each combonation of Color and Cut. We see that the J-Premium has the highest average price (`$6,287`), while E-Ideal has the lowest average price (`$2,601`). This could indicate that the color has more of an affect on price than the cut does.

![Visualization 3](./images/price_cut_color.png)

## Conclusions/Recommendations
I trained 3 different regression models to predict the diamond price based on the characteristics. The models were Linear Regression, Random Forest, K Nearest Neighbors (KNN) 

Below are the results. 

### R2 Scores

| Model | Score |
| ----- | ----- |
| Linear Regression | 0.92 |
| Random Forest | 0.98 |
| KNN | 0.97 | 

The R2 score tells us how much of the predicted price can be explained by the model. In the case of Linear Regression, it can explain 92% of the variance of the prediced price. Meaning that the remaining 8% may be due to factors outside of this dataset. Meanwhile, KNN can explain 97% of the variance, so it can explain 97% of how/why it determined the price differs from the average. 

### RMSE Scores

| Model | Score |
| ----- | ----- |
| Linear Regression | 1108.86 |
| Random Forest | 534.8 |
| KNN | 728.19 | 
| Baseline | 3920.46 |

The RMSE scores tell us how much, on average, the predicted prices differ from the actual prices. So for Linear Regression, the model can predict the price within \\$1108.86 on average, while the Random Forest model can predict it within \\$534.8. 

Unfortunately, while the Random Forest model performs better, the resulting model is too large for GitHub to store, so the flask app within this repository utilizes the KNN model. 

## Additional Information
Dataset comes from [Kaggle](https://www.kaggle.com/datasets/shivam2503/diamonds)
