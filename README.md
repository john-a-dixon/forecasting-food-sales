# Forecasting Food Sales

_John Andrew Dixon_

---

## Overview

The goal is to analyze past sales data to find relationships that can hopefully optimize an outlet's future sales and help them make better financial choices.

## Insights

The primary insights garnered from my analysis deal with outlet location, outlet type and their corresponding sales.

### Outlet Location & Sales

The bar graph below shows that location correlates with sales. It's not that location choise causes better sales though I can say that if an outlet chooses a location of **Tier 2** they _may_ likely have better sales.

<p align="center">
  <img src="/assets/locationvsales.png" width="60%" height="60%">
</p>

### Outlet Type & Sales

The bar graph below shows that the type of outlet correlates significantly correlates with sales. Like above, it's not that outlet type causes better sales though it's very important that an outlet considers what type they are if they wish to likelier have higher sales. It's apparent that **Grocery Store** outlets make the least while **Supermarket Type 3** outlets are bound to make a good amount. 

<p align="center">
  <img src="/assets/typevsales.png" width="60%" height="60%">
</p>

Of course, this is all according to this dataset and it could be that the dataset just so happened to have the highest earning Supermarket Type 3 stores and the lowest earning Grocery Stores. Though, just judging by this dataset, I'd say an outlet who is of **Supermarket Type 3** and in location **Tier 2** is likely to make a good sales.

## Model & Metrics

For future sales predictions, I tested out two machine learning models: linear regression and decision tree regression. A quick error metric summary of each is as follows:

- Linear Regression
    - R<sup>2</sup>: 0.5806 (58.06%)
    - MAE: $789.25
    - RMSE: $1067.66
- Decision Tree Regression
    - R2<sup>2</sup>: 0.6114 (61.14%)
    - MAE: $721.64
    - RMSE: $1027.73

In summary, the decision tree produced better predictive results than the linear regression. But, the decision tree's predictive capabilities are still suspect. It can only account for 61.14% of the variations within the target prediction. That is pretty mediocre, and is especially bad when it comes to money. Likewise, its high RMSE means that it produces larger errors. Once again, bad when it comes to money.

## Final Recommendations
