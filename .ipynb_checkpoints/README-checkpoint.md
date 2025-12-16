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

#### Visualization 1: [Title]
[Description and interpretation of the first visualization.]

![Visualization 1](./images/carat_price_cut.png)

#### Visualization 2: [Title]
[Description and interpretation of the first visualization.]

![Visualization 2](./images/price_kde.png)

#### Visualization 3: [Title]
[Description and interpretation of the second visualization.]

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
Include any additional information, references, or resources that might be relevant for understanding the analysis.

---

Feel free to replace the placeholders with your actual content. Additionally, if you have images for your visualizations, make sure to replace the placeholder paths with the correct file paths or URLs.

Once you've filled in the content, save the file with a `.md` extension (e.g., `README.md`). You can use this Markdown file on platforms like GitHub to provide a well-structured README for your analysis.
