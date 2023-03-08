# Forecasting Food Sales

_John Andrew Dixon_

---

## Overview

The goal of this project is to analyze past sales data and find relationships that can hopefully optimize an outlet's future sales and help them make better financial choices.

Here is a data dictionary of the analyzed dataset:

|**Variable Name**        |**Description**                                                                                    |
|-------------------------|---------------------------------------------------------------------------------------------------|
|Item_Identifier          |Unique Product ID                                                                                  |
|Item_Weight              | Weight of product                                                                                 |
|Item_Fat_Content         |Whether the product is low fat or regular                                                          |
|Item_Visibility          |The percentage of total display area of all products in a store allocated to the particular product|
|Item_Type                |The category to which the product belongs                                                          |
|Item_MRP                 |Maximum Retail Price (list price) of the product                                                   |
|Outlet_Identifier        |Unique store ID                                                                                    |
|Outlet_Establishment_Year|The year in which the store was established                                                        |
|Outlet_Size              |	The size of the store in terms of ground area covered                                             |
|Outlet_Location_Type     |The type of area in which the store is located                                                     |
|Outlet_Type              |Whether the outlet is a grocery store or some sort of supermarket                                  |
|Item_Outlet_Sales        |Sales of the product in the particular store. This is the target variable to be predicted          |

## Insights

The primary insights garnered from my analysis deal with `Outlet_Location_Type`, `Outlet_Type` and their corresponding `Item_Outlet_Sales`.

### Outlet Location & Sales

The bar graph below shows that `Outlet_Location_Type` correlates with `Item_Outlet_Sales`. I won't say that location choice causes better sales though I can say that if an outlet chooses a location of **Tier 2** they _may_ likely have better sales.

<p align="center">
  <img src="/assets/locationvsales.png" width="60%" height="60%">
</p>

### Outlet Type & Sales

The bar graph below shows that `Outlet_Type` correlates significantly with `Item_Outlet_Sales`. Like above, I won't say that outlet type causes better sales though I do believe it's very important that an outlet considers what type they are if they wish to potentially have higher sales. It's apparent that **Grocery Store** outlets make the least while **Supermarket Type 3** outlets are bound to make a good amount. 

<p align="center">
  <img src="/assets/typevsales.png" width="60%" height="60%">
</p>

Of course, this is all according to _this_ dataset. It could be that the dataset just so happens to have the highest earning Supermarket Type 3 stores and the lowest earning Grocery Stores, thus causing the results to misrepresent reality. However, just judging by this dataset, I'd say an outlet who is of **Supermarket Type 3** and in location **Tier 2** is likely to make a good sales.

## Model & Metrics

For future sales predictions, I tested out two machine learning models: linear regression and decision tree regression. A quick error metric summary of each on the test set is as follows:

- **_Linear Regression_**
    - _R<sup>2</sup>_: 0.5806 (58.06%)
    - _MAE_: $789.25
    - _RMSE_: $1067.66
- **_Decision Tree Regression_**
    - _R2<sup>2</sup>_: 0.6114 (61.14%)
    - _MAE_: $721.64
    - _RMSE_: $1027.73

In summary, the decision tree produced better predictive results than the linear regression. But, the decision tree's predictive capabilities are still suspect. It can only account for 61.14% of the variations within the target prediction. Additionally, the fact that the predictions will be off on average by $721.64 is pretty awful. It's especially bad when since faulty predictions can cause a loss of money. Likewise, the high RMSE means that it produces larger errors. Once again, bad when it comes to money.

## Final Recommendations

I have a few recommendations:

1. If an outlet has a choice of `Outlet_Locatio_Type` and `Outlet_Type` choose a location of **Tier 2** and a type of **Supermarket Type 3**. Though these may not necessarily cause the outlet to generate more food sales, something about them may likely help the outlet gain more sales.
2. Get a better dataset if predictions want to be made. Or, find a better machine learning model to make predictions. Or, do both. I say this for a few reasons:
    - The predictive analysis I did (see above) had two models with poor predictive power. Maybe trying a different model will change this and offer better metrics.
    - It's possible that the machine learning models are not the problem. Instead, maybe its the dataset that's the problem. That is, the dataset itself, no matter the model, may not produce good predictions. In this case, a better dataset should be used.

