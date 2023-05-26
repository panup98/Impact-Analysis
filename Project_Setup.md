# Project Background

SHH is actively allocating resources towards the pursuit of securing earned media coverage, 
recognizing its potential to inspire donor engagement and prompt action. 

However, presently, there lacks a reliable means of measuring and quantifying the precise 
influence that earned media has on individuals' decisions to contribute donations. 

Consequently, the task of devising an impactful media strategy becomes increasingly arduous, 
as it necessitates navigating the intricacies of determining where to allocate resources 
effectively and accurately predicting the outcomes of media exposure.

# Problem Statement

* How different media channels drive donations outcomes for SHH? Which earned media channel to focus on?
* How can Second Harvest Heartland (SHH) predict donation activity in relation to media exposure?

# Assumption

In this project, we have made several assumptions to account for various factors that can affect the process of donation.

1. **Difference in Donation Dates**: We have observed that there is often a time gap between the actual date of donation and the 
date when the donation is received. To accommodate this difference, we have made the following assumptions for different 
donation methods:

- Cash donations are assumed to have a one-day offset between the actual date of donation and the date of receipt.
- Card donations are assumed to have a two-day offset.
- Cheque donations are assumed to have a four-day offset.
- Donations in the form of stocks and property are assumed to have a six-day offset.


2. **Influence of Media Sources**: We have also considered the impact of various media sources on the donations received. 
Different media platforms can have varying effects, and we have assigned weights to reflect their contribution towards donations. 
The assumptions made are as follows:

- TV sources are assumed to have a one-day effect on donation trends.
- Radio sources are also assumed to have a one-day effect.
- Web sources, such as online platforms, are assumed to have a longer-lasting impact of three days.


3. **Diminishing Influence of Media**: We have taken into account that the contribution of media towards a donation decreases as 
the difference between the article date and the donation date increases. This means that if there is a significant time gap
between when an article promoting a donation campaign is published and when the actual donation is made, the influence of 
that article on the donation may be reduced.

By considering these assumptions, we aim to analyze and understand the factors that affect the timing and impact of donations, 
particularly with respect to different donation methods and media sources.

# Exploratory Analysis

For our project, we conducted an exploratory analysis to gain insights into the behavior of individual donors in the United States. 
Since our client's main focus was on US donors, we specifically utilized the records pertaining to these individuals, which accounted 
for 94% of the entire dataset.

Upon analyzing the data, we discovered that donations were primarily concentrated around the state of Minnesota, while being fairly 
distributed across the rest of the country. In order to capture this geographical aspect, we introduced a new attribute that indicated
whether the donation was associated with Minnesota or not.

Furthermore, we identified a notable trend where donations during festive seasons tended to be higher compared to non-festive periods. 
To account for seasonality, we incorporated the month as an additional column in our dataset.

To further refine our analysis, we offset the data based on the mode of transaction. This adjustment allowed us to observe a new distribution,
which we utilized for our subsequent analysis.

Additionally, we observed that a greater number of donations were received later in the week, specifically from Thursday to Sunday. 
This finding prompted us to explore whether media sources associated with these days of the week generated more donations. 
Upon examining the results, we found that media sources occurring towards the end of the week indeed generated a higher number of donations.

# Impact of Media Sources on Donations: Exploring the Relationship

In this project, our aim was to examine how different media sources and their characteristics influence donation patterns. To achieve this, we employed linear models for analysis. Initially, when we considered only the media channels, we found that the models could not adequately account for the variations in donation amounts. However, through further investigation and the inclusion of derived variables, we were able to develop a more effective model that explained 70.24 percent of the variability in donations associated with each media source.

Key Findings from the Linear Model:

1. **Influence of Web Sources vs. Radio Sources on Donations**:
Our analysis revealed that donations generated through web sources were higher compared to those from radio sources. While both web and radio channels had a significant impact on donations, the disparity between the two was notable. Specifically, when all other factors remained constant, the difference in donations between web and radio sources amounted to 1522 units.

2. **Effectiveness of Campaigns in Different Months**:
Campaigns conducted in September and October were found to be more effective in generating donations compared to those held in January. Specifically, when all other factors were held constant, September campaigns resulted in 5366 units more in donations, while October campaigns yielded 5310 units more in donations, both relative to January campaigns.

3. **Influence of Articles Mentioning the Word "Donation"**:
Our analysis revealed that articles containing the word "Donation" had a significant impact on the amount of donations received. Specifically, when compared to articles that did not mention the word "Donation," the difference in donations amounted to 2500 units, assuming all other factors remained constant.

4. **Influence of Articles from Minnesota vs. Other States**:
Articles originating from Minnesota were found to generate more donations compared to articles from other states. Specifically, when all other factors were held constant, the difference in donations between articles from Minnesota and those from all other states amounted to 1370 units.

These findings highlight the various factors related to media sources that influence donation amounts. Understanding these relationships can help organizations and campaigns optimize their strategies for maximizing donations.

# Predictive Model

In our project, we have developed a predictive model to estimate certain performance metrics. To evaluate the accuracy of our model, we have chosen RMSE (Root Mean Square Error) as the performance metric.

RMSE is a statistical measure that quantifies the differences between the values predicted by our model and the actual observed values. It provides an indication of how much our predictions deviate from the true values.

We specifically chose RMSE because it is measured in the same units as the predicted value. This means that the RMSE value directly relates to the magnitude of the prediction errors. By using RMSE, we can easily interpret and compare the performance of different models.

Our best model, which outperformed the base linear model, is the Regression Tree Model with an RMSE of 2793. In the context of RMSE, a lower value indicates better performance. Therefore, our model's lower RMSE value demonstrates that its predictions are closer to the actual values compared to the base linear model.

Furthermore, to assess the performance of our regression tree model on unseen data, we measured the RMSE on holdout data, which resulted in an RMSE of 4546. This value represents the prediction errors of our model when applied to new data that was not used during the model development process.

The main purpose of our predictive model is to predict performance metrics, such as the Return on Investment (ROI) on earned media. Additionally, we aim to compare the output amounts of different inputs to gain insights into customer behaviors. To continuously improve the model's performance, we regularly update it with new and real data. This ensures that our predictions align with the most up-to-date information available.

# Recommendations

1. **Focus on Minnesota Media**: On average, Minnesota media generates 6.3 times more donations compared to non-Minnesota media. Therefore, it is recommended to prioritize Minnesota-based media outlets for the project.

2. **Emphasize Web Conten**t: Among non-Minnesota media, web content generates 2.4 times more donations compared to non-web media. It is advisable to give more attention to online platforms and digital content to maximize donation outcomes.

3. **Incorporate Donation Keyword in Articles**: Articles that specifically highlight the topic of donation have shown to attract significantly more donations. Our analysis indicates that incorporating the keyword "donation" can lead to approximately 2500 additional donation amounts, as observed in the linear model we developed.

4. **Schedule Media Posts for Thursday to Sunday**: Based on our exploratory analysis, data suggests that media posts published towards the end of the week, specifically from Thursday to Sunday, tend to generate more donations. It is recommended to plan and release media posts during these days to optimize donation outcomes.



