# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2: Predicting House Prices in Ames, Iowa

### Background

Opendoor Technologies Inc is a digital platform for transacting in residential real estate headquarterd in San Fracisco. Opendoor aims to reinvent the real estate experience through making it possible to buy and sell property on a mobile device.

Opendoor has created a new model for selling a home, called iBuying. To summarize the business model, property owners can bid to sell their properties through the Opendoor app or website. Opendoor will purchase the property as-is, and then make necessary repairs before relisting the property. More information on Opendoor and their business model can be found [here](https://www.opendoor.com/w/faq/what-is-opendoor).

Opendoor currently offers their services to 27 markets in the US, and is now looking to expand their service to Iowa. As part of their market analysis, Opendoor would like to do a case study on the housing market in Ames, Iowa.

Using historical data from the Ames Assesor's Office on individual properties sold in Ames from 2006-2010, Opendoor has tasked their data science team to build a model that can be used to predict the selling price of various houses across Ames, Iowa. More information on the dataset can be found [here](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt).

Opendoor will use this model as a benchmark to assess whether to accept a bid for a property based on a property's features. In addition, Opendoor would like to know:
1. Which particular neighborhoods in Ames are most profitable?
2. Which particular type of residential properties in Ames are most profitable?
2. Which features should Opendoor focus on renovating to maximize their returns when re-listing the properties?

---

### Problem Statement

The goal of this project is to build a linear regression model that can predict the selling price of houses across Ames, Iowa. Additionally, this project aims to provide insights on:

1. Which particular neighborhoods in Ames are most profitable?
2. Which particular type of properties in Ames are most profitable?
3. Which features are most important to renovate in order to maximize returns on a property?

---

### Summary of Analysis

For this project, I trained multiple models including a baseline model, Linear regression (with no regularization), Ridge regression and Lasso regression models. I evaluated my models by comparing the R2 score for my train, test, and cross validation sets, which allowed me to assess if my models were overfitted or underfitted. I also compared the R2 score and RMSE for my test data between each model so I could see how well my models performed on new data.

The model I chose as my final production model was a lasso regression model with hyperparameter tuning and some additional feature engineering. This model was a good fit and performed well on my test data set, with an R2 score of 0.92584 and an RMSE of 19857.76 USD. For comparison, the baseline RMSE when using the mean sale price from the training data set was 82556.99 USD.

---

### Conclusion and Recommendations

I would recommend Opendoor to focus on the following neighborhoods and types of dwellings:

- Neighborhoods: I would recommend purchasing properties in Green Hills, Stone Brook, and Northridge Height. If all other features are constant:
> - A house in Green Hills will sell for 110K USD more than a house in another neighborhood
> - A house in Stone Brook will sell for 34K USD more than a house in another neighborhood
> - A house in Northridge Height will sell for 20K USD more than a house in another neighborhood

- Types of dwellings: While a 1-1/2 Story Unfinished house will sell for 45K USD more than another type of dwelling if all other features are constant, this type of property is not very common and only 0.05% of houses sold between 2006 and 2010 are of this type. Therefore, I would recommend focusing on the following two types of dwellings:
> - 1-Story 1946 and Newer Style Houses. 38% of the houses sold in Ames between 2006 and 2010 are of this type. If all other features are constant, this type of dwelling will sell for 29K USD higher than other types of dwellings
> - 2-Story 1946 & Newer houses. 19% of the houses sold in Ames betweeb 2006 and 2010 are of this type. If all other features are constant, this type of dwelling will sell for 26K USD higher than other types of dwellings

Finally, some other features that Opendoor may find beneficial to renovate before re-listing properties are:
- If Opendoor is able to increase the area or build additional rooms in an unfinished property:
> - In general, if all other features are constant, increasinng the total living area (including the basement) would increase the price of the house by 33USD per square ft.
> - In particular, I would ensure that the basement is complete as an unfinished basement does decrease the price of the house by 17USD per square ft. In contrast, every square ft of finished basement space increases the value of the house by 7 USD if all other features are constant.
> - Additionally, increasing the total number of rooms would increase the selling price of the house by 1.7K USD per room, and increase the total number of bathrooms would increase the selling price by 1.8K USD per room.
-  Lastly, a quick win where possible would be to increase the number of fireplaces, or the quality of the fireplace. From all the miscellanious features (such as the pool, kitchen, fence, etc), the fireplace is the only feature with a statistical significance at a 95% confidence level. Increasing the rating of the fireplace by 1 unit will increase the value of the house by over 900USD, if all other features are constant.
