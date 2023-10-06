# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Ames Housing Data and Kaggle Challenge

# Predicting Housing Sale Price for New Real Estate Development Project
---

The designs for a new development project have been signed off to redesign and modernize Ames. The developers are looking to understand the sale price of the houses in the area to better understand the cost of purchasing the land and ensuring individuals are appropriately compensated during the transaction. 

The objective of this project, will be to understand how the square footage of different areas within the property affects the sales price, then predict and estimate value on the houses by utilizing a regression model. 
<br>

---
## Research

Real estate development projects going through long and meticulous planning processes before they can even break ground. Think about the times that you have wanted to or have done work to your own house, it could be as small as changing the sink or shower to extending your property for more space but lets amplify that a little bit. With large level projects the planning stage could range from 6 months to 6 years. 

In the cases of large development projects like this investors and developers will initially do research to understand and identify areas that could benefit from significant development, whether that involves more houses or modernizing the city/town to accommodate for newer businesses or shopping malls. Now of course, the larger the project the longer the planning process will take and the more hoops that need to be jumped through and paper work that needs to be done to get sign off.

When performing these large scale projects especially when housing is taken into consideration, affordability for the end user needs to be taken into consideration aswell. In these situations most developers will create a selection of houses that can be more affordable, benefitting both parties, for the investors it means the properties are easier to sell and the buyer is able to get into a new property at a lower cost. However, inorder to do this, developers will look to find ways to cut initial costs or even presell houses before the construction begins, leading to the horror stories that some of us have may have heard about poorly built homes as we can see one explain reported by Daily Mail, https://www.dailymail.co.uk/news/article-4310428/Buyers-new-build-homes-reveal-property-nightmares.html.

(https://lev.co/blog/assets/real-estate-development-timeline/#:~:text=Your%20project%20could%20take%20six,stages%20of%20the%20development%20process).
(https://lichfields.uk/blog/2016/november/8/start-to-finish-how-quickly-do-large-scale-housing-sites-deliver/)

---
## Data Dictionary
---
The full data dictionary used within this project can be found at:https://www.kaggle.com/competitions/dsi-910-ames-housing-challenge/data

The data dictionary below contain the information about the data within the selected train data csv file.

---
|Feature|Type|Dataset|Description|
|---|---|---|---|
|Id|*Int*|544|Identifying number for each property|
|Overall Qual|*int*|6|Categorical data giving the property a ranking of its overall quality ranging from 1 to 10|
|Year Built|*int*| 2006 |The year the property was built |
|Full Bath|*int*| 2 | Number of full baths |
|Half Bath|*int*| 1 | Number of Half Baths|
|Garage Area|*float*|475.0|The size of the garage in square feet|
|Total Bsmt SF |*float*| 725.0 | The square footage of the Basement |
|Gr Liv Area|*int*| 1479 | Above the ground living area square feet |
|1st Flr SF|*int*| 725 |The square footage of the 1st floor|
|2nd Flr SF|*int*| 754 |The square footage of the 2nd floor|
|SalePrice|*int*| 130500 | The sale price of the property |

---
## Executive Summary
---
Development projects of any scale are a costly and lengthy process, whether you are having construction work done on your own house, or looking to build a new house for yourself. However, some of the largest scale projects reach figures that most of us can not comprehend, with the top 2 largest projects costing "US$500 billion" and "US$113 billion" (https://www.international-construction.com/news/7-of-the-world-s-most-expensive-construction-projects/8026711.article) as reported by international construction. 

In this project we will be looking to understand what how much the developer will need to spend in the first stage of the process, in which they need acquire the land. In order to do this we will looking to identify the categories that contribute the most to the price of the house and utilise this data to create an efficient model that will help us understand the initial cost whilst also ensuring that property owners are fairly compensated.


---
## Methodology
---

The first step will be to identify how the didn't features affect the price of the house however, with the developers end goal its just the land that the property sits on, the main focus will be to create a model created from the square footage and area data.

Once we have selected the data, we will look to create our baseline Linear Regression model as the data is found before we introduce any preprocessing or feature engineering techniques to ensure that we are able understand how they affect how the model performs.

---
# Conclusion & Recommendations
---

In conclusion we were able to predict that it would cost $157,135,272.02 with estimate variation of $17,141,656.37. We determined this by utilizing a Ridge CV Regression model, with the data going through Polynomial and Standard Scaling preprocessing. 

---
|Model|R2 Score(train)|R2 Score(Val)|MAE|RMSE|Description|
|---|---|---|---|---|---|
|Model 1|0.771023|0.835513|23307.513959|31779.748064|Baseline|
|Model 2|0.886713|0.852980|21157.810887|31094.158241|Poly|
|Model 3|0.777809|0.807667|25021.056681|35564.524098|Dropped Full Bath and Half Bath|
|Model 4|0.780299|0.811278|24684.392809|35229.123817|StandardScaled|
|Model 5|0.885289|0.871826|19836.248501|28053.375859|Poly and SC|
|Model 5|0.880983|0.877115|19523.526618|27468.513989|RidgeCv|

---

From initial looks at the R2 graph, we would assume that model 2, 5 and 6 have very little difference between the them. However when looking at the Mean Absolute Error (MAE) and the Root Mean Square Error(RMSE), the difference becomes a little more obvious. With these values showing the variation between the evaluation prices and the testing prediction, we want to ensure that we select model with the smallest difference to ensure that we can fairly compensate the home owners which is why we have decided to select model 6 as our final model.

This also helps understand how the preprocessing and feature engineering helped improve the performance of our model. As we can see that introducing Polynominal features on its own only made a small difference to both the MAE and RMSE, but utilising the Standard Scalar to help scale the variables to unit variables, especially in the case of mixing categorical and numerical data around 4000 reduction to both the scores from model 1 to model 5.

When we compare model 5 and model 6, where both these models were trained with the same data, with model 5 using a Linear Regression model and model 6 using a Ridge CV Regression model. I believe model 6 performed better, one due to the added regularization that the Ridge model, helping control the polynomial features and standard scaling that was implements on the data and handling multicollinearity with the data points that highly correlated with the sale price, as we saw within the heatmap during our EDA. The Ridge model also helps prevent overfitting, especially in the case of utilisinng small datasets, ensuring that the model doesn't only work with the training data but also works with any new data that is introduced to the model.

To take this model further, I would recommend trying to introduce more details of the house to see how that affects the predicted values. Do a deeper dive into Neighborhood and House style and lastly investigate if Year of remodel and additional constructions changes the model 



---
# Citations and Special Mentions
---
Ames Housing Data:  "https://www.kaggle.com/competitions/dsi-910-ames-housing-challenge/overview"
7 Most Expensive Construction Projects: "https://www.international-construction.com/news/7-of-the-world-s-most-expensive-construction-projects/8026711.article"
Real Estate Development Timeline: "https://lev.co/blog/assets/real-estate-development-timeline/"
Thanks to Rowan and Tim for answering all my endless questions