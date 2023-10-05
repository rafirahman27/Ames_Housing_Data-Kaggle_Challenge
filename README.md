# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Ames Housing Data and Kaggle Challenge

# Predicting Housing Sale Price for New Real Estate Development Project
---

The designs for a new development project have been signed off to redesign and modernize Ames. The developers are looking to understand the sale price of the houses in the area to better understand the cost of purchasing the land and ensuring individuals are appropriately compensated during the transaction. 

The objective of this project, will be to predicted and estimate value on the houses by utilizing a regression model. 
<br>

---
## Research

Real estate development projects going through long and meticulous planning process before they can even break ground. Think about the times that you have wanted to or have done work to your own house, it could be as small as changing the sink or shower to extending your property for more space but lets amplify that a little bit. With large level projects the planning stage could range from 6 months to 6 years (https://lev.co/blog/assets/real-estate-development-timeline/#:~:text=Your%20project%20could%20take%20six,stages%20of%20the%20development%20process).



## Data Dictionary
---
The full data dictionary used within this project can be found at:https://www.kaggle.com/competitions/dsi-910-ames-housing-challenge/data

The data dictionary below contain the information about the data within the selected train data csv file.

---
|Feature|Type|Dataset|Description|
|---|---|---|---|
|Selected Train Data|  |  |
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

To identify the Top 10 countries we will be talking the population and number of doctors per 1000 data found on gapminder to identify the countries that have the least amount of doctors. The population of the countries must be considered to ensure a fair comparison is made. For example if both Country A and B have 10,000 doctors, you would initially think they are the same. However if  A has a population 1 million and B has 4 million, your interpretation changes, now we can see that country B would be higher in the ranking for least accessible healthcare system.

In order to do this, I will be calculating the average number of doctors for each country, to accomdate for any missing data from across the years. The missing date could be due to a number of things such as, the governments not having the resources or not having the money to consistently collect the data or many other reasons. To ensure that data wasn't simply dropped and missing out on countries that could potentially be at the top of the list an average will be calculated. The exception to this will if a country only has 1 data point, we can not assume that number hasn't changed, resulting in that country being dropped.

Additionally, as the data provided is doctors per 1000 people. We will be set the assumption that by dividing the number by 1000 and multiplying by the population we can workout how many doctors there are in total.

When looking into the money invested into healthcare we looking at the amount of money the government has on average spent per a person. We will be taking that data and multiplying it by the population and then calculating the mean in order to understand how much each country has invested into their healthcare industry over the last 10 years.

---
# Conclusion & Recommendations
---
In conclusion we were able to create the following list which shows the Top 10 countries that have the least amount of doctors that could potentially benefit from receiving additional support from Doctors Go Anywehere. In order to better understand these results we also looked at the amount of money each country invested into their population's healthcare and looked at the country's average life expectancy.

---
|Ranking Position|Lowest amount of Doctors Country|Lowest amount of money spent Country|Lowest Average Life
|---|---|---|---|
| 1 | Ukraine | Ukraine  | Eritrea |
| 2 | Naura | Naura | Kiribati |
| 3 | Slovenia | Slovenia | Nauru |
| 4 | Gambia | Gambia | Gambia |
| 5 | Colombia | Colombia | Sao Tome and Principe |
| 6 | Kiribati | Kiribati | Ukraine |
| 7 | Sao Tome and Principe | Sao Tome and Principe | Egypt |
| 8 | Turkey | Turkey | St. Kitts and Nevis |
| 9 | St. Kitts and Nevis | St. Kitts and Nevis | Brazil |
| 10 | Egypt | Egypt | China |

---
From the list above we can make the assumption that on average the less a country spends on their populations healthcare, the less doctors that population will have access to. Now this is still as they could be other factors involved for example the education system not being developed enough.
<br><br>
When comparing the average life expectancy to the lowest amount of doctors we can see that the list has changed up. With 3 new location popping up; Eritrea, China and Brazil. This raises an interesting question as all 3 where found in the Top 10 highest healthcare contribution by the government as you can see from the list below. As a recommendation I would suggest to look further into why this could potentially be the case.
<br><br>
I would also recommend find data regarding private healthcare to see how it could potentially change these finding as many countries do rely more on the private services that are available.

---
|Ranking Position|Highest Healthcare Contribution Countries|
|---|---|
|1| Japan |
|2| Czech Republic|
|3| Fiji|
|4| Italy|
|5| Canada|
|6| Eritea|
|7| China|
|8| Netherlands|
|9| Austrialia|
|10| Brazil|

---
Some more recommendation that can be made from my findings are list below:
1) Understand how China a significantly large amount of Doctors whilst having a low amount of contribution from the government
2) Investigate Why China and San Marino took a deep in life expectancy from 1995 to 2002
3) Investigate how Japan has one of highest life expectancies with a low amount of Doctors compared to the rest.

---
# Citations and Special Mentions
---
Data Collected from Gapminder "https://www.gapminder.org/data/"
Research and quotations from The Guardian "https://www.theguardian.com/doctors-without-borders/2022/nov/21/msf-doctors-without-borders-year-in-review"
Thank you to Tim Book(GA Staff), Rowan Schaefer(GA Staff) and Piotr Jankowski(friend) for helping debug, simplify and understand