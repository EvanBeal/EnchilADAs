---
layout: page
title: Is Ethnicity reflected in Food Purchase?
cover-img: "/assets/img/fish_chips.jpg"
subtitle: Analysis of Tesco and socio-economic data of Londoners
---

## London, a city of diversity
London is one of the most populated cities in Europe. With almost 9 millions of inhabitants, the population comes from all walks of life. Therefore, a great heterogeneity appears between the Londoners, which can be mirrored at the level of their age, financial means or origins and ethnicities for instance.

This heterogeneity can be pictured with the different areas of the city. Indeed, living close to Buckingham Palace and being in daily contact with the Queen and the Prime Minister  is only accessible to a population with really significant financial means, resulting in less heterogeneity in this district from an economic viewpoint. In contrary, we can easily imagine that living in the suburbs offer some great advantages to a wide range of people, resulting in areas with really diverse inhabitants. 

To determine whether our ethnicity is one of the factor that could influence our food purchase, we would like to capture this heterogeneity present in the different areas of the city. Therefore, the analysis has to be done at the area level and many possibilities appear to subdivide London into different districts. One can consider the 32 Boroughs for example. However, those areas are very large (from 150k to 300k inhabitants) and may not be really representative of everyone's diversity. That's why we decided to conduct our analysis at the Lower Super Output Area (LSOA) level, the finest subdivision of the city possible. Those 4'833 areas have an average population smaller than 2k and therefore offer a great resolution to link the food purchase to the diversity of the Londoners. 

## Tesco, "Every little helps"  
With this slogan, Tesco wants to be close to the population. This is one of the reason that allowed this British groceries and general merchandise retailer to become a multinational and the market leader of groceries in UK with more than a quarter of the market share. This position of leader renders the data of its customer really valuable to link food purchases to a number of socio-economic factors. That's why the Tesco Grocery 1.0 dataset, a record of the food items purchased by 1.6 M Tesco customers, came out with a great interest to perform multiple studies. 

This dataset has been proven to be ecologically valid by comparing the food purchases with metabolic syndrome conditions that are strongly linked to food consumption habits, in the paper [Tesco Grocery 1.0, a large-scale dataset of grocery purchases in London](https://www.nature.com/articles/s41597-020-0397-7). We extend it with the [LSOA atlas](https://data.london.gov.uk/dataset/lsoa-atlas), an official dataset reporting census data at LSOA level, which gives us information on the distributions of different ethnic groups accross London. Using both those sources, we will try to see if the prevalence of different ethnic groups have an impact on the content of the food basket of Tesco's customer.

## How can we determine the effect of ethnicity on food purchase?
Our main question of interest being to find out whether the appartenance of customer to a certain ethnic group influence their way of shopping in Tesco stores, two main analyses have to be performed in order to identify potential **correlation** and **causality** between the ethnicity and the food products purchased. 

Throughout this datastory, you will have the opportunity to observe the links between different combination of ethnic groups prevalence and food categories purchased, guided by the main results we obtained, in order to establish some food purchase patterns that appear to be specific of certain ethnic groups. 

Following the common thread of our analysis based on the following pairs of features (white ethnic group and ready made food category, black ethnic group and fruits & vegetables food category, asian ethnic group and fats oils food category) you will be able to draw your own conclusion on the examples that spark your curiosity.

## Correlation analysis
### Correlation of ethnicities with food categories purchased in Tesco
To begin our analysis, we want to see if there are some relations between the different product categories and the ethnic groups. A simple approach to look if some relations exist between two features is to look at their correlation. Indeed, if there is no correlation between them, we can't expect any causal relations to be present. Therefore, with this first outlook, we get an idea on a potential reflect of the ethnicity on food purchase and even more precisely if there is some postive or negative links between the ethnicities and the food categories purchased in Tesco. 

### First look of the correlation between the items bought in Tesco stores and the ethnicities of the different areas
Those two first figures allow to visualize how the prevalence of certain ethnic groups correlate with the probability of certain products categories to appear in a typical shopping cart. The two visualizations allow to look at those data from different points of view:
- How does the prevalence of a specific ethnic group correlate with the prevalence of the different product categories ?
{% include corr_bar_plot_all_items.html %}


- How does the prevalence of a specific product category is correlated with the prevalences of the different ethnic groups ?
{% include corr_bar_plot_all_eth.html %}

We can indeed see that the composition of the typical shopping cart is linked with how much certain ethnic groups are represented in the area where the purchases are carried. Looking at our three features pairs of interest, what we can conclude from those plots is that:
- The white ethnicity is positively correlated with the fraction of food products represented by the ready made meal category. This means that a higher representation of the white ethnicity is typically linked to a higher representation of ready made meal in shopping cart of Tesco customers. 

- The black ethnicity is negatively correlated with the fraction of fruits and vegetables. A higher representation of the black ethnicity is typically linked to a lower representation of fruits and vegetables in the food products.

- The asian ethnicity is positively correlated with the percentage of fats and oils purchased, a higher representation of the asian ethnicity is linked with a higher representation of fats and oils in comparison to the other food products categories.

### Map visualization of the correlation
We can also try to assess the correlation visually by comparing how the ethnicities are represented in the different areas of London and how the fraction of products category purchased vary on maps of the London LSOA. 
You can try to look at some combinations of the correlated features and see if visually you can identify those positive or negative correlations. 

#### Food Purchase in London
{% include map_food_small.html %} 

#### Ethnic groups in London
{% include map_ethnicity_small.html %}

Considering the white ethnicity and the fraction ready made meals, the positive correlation can be indeed well observed. It appears that the fraction of ready made meals purchased in Tesco increases the further away from the center of London you go, especially in the South and East suburbs where we can also observe areas with a high percentage of population having a white ethnicity.

However, to determine if there is a real causality effect and being able to establish whether our ethnicity is really reflected in some of the products categories we purchased, it's really not enough to consider only this **correlation** study and the visualization. For example, in some cases two features can be highly correlated, but because of the presence of one or more confounders, no causal link can be established. A confounder can be described as a variable that influences the two features for which we are interested to dermine a causality link, causing a spurious association misleading the analysis.
Therefore, a more complex study should be performed, accounting for those factors and which will be this time a **causality** study.

## Causality analysis 
To get a first sense on wether a causality link will exist between some ethnicities and specific food products categories, we first decided to explore whether a causal link exists between two features representative of the diversity of the areas in terms of: 
1. ethnicity 
2. food products categories purchased

Besides those two features, it's important to consider this time other socio-economic factors. Those ones may also be correlated with the ethnicities and the categories of products bought in Tesco acting therefore as potential confounders in the causality effect we aim to observe. 

### Which factors may also be linked to the diversity of food purchase?
Many factors in addition to the appartenance to a specific ethnic group may be linked in fact to your food habits. We can mention for instance, your age, your salary, whether or not you have a job or whether or not you are in good health. These factors have to be considered in our study to not draw causal links that may have been explained in fact by one of those factors.

Let's explore how some of those factors are linked to diversity of ethnicity and food purchases before considering all those potential confounders in the causality analysis.

### Richness, employment rate or age: real confounders?

To get an idea of the effect of those different features on food purchase diversity (the richness feature being the median income per household of the area), we can analyze the results obtained with a linear regression analysis. This technique allows to observe the linear relationship between the features, as well as how precisely the food purchase diversity values can be predicted using one or a combination of features.

This is what is represented with the following plot. It allows to observe the results of a linear regression between the food purchase diversity and the selected features. The scatter plot allows to get a first sense on how well the given features can predict this diversity feature and the bar plot allows to assess statistically the results observed with the coefficient of determination of the model. This value is equal to one if a perfect linear relationship exists between the features. 

#### Linear Regression
{% include reg_plot.html %}

By testing the different combinations of features we can observe that the food purchase diversity is best predicted when using all the different features considered. Looking at the features individually, it can be seen that the median income feature allows to obtain the best prediction results, followed by the ethnic diversity feature. This is interesting as it suggests that the diversity of ethnicity is a feature with a great linear relationship with the food purchase diversity but not the greatest relationship. That's why we need to consider those additional socio-economic factors to not conduct misleading interpretations of the results observed. 

Now that we have observed that a linear relationship exists between the food purchase diversity and median income, employment rate, age and ethnicity diversity, let's look at how those features interact together.
With the following plot you can indeed observe some interactions and see for example if the population of the richest areas of London will tend to buy products from many different food categories and if the inhabitants represent many different ethnicities or not. 

#### How those features are linked together
{% include rich_employ_age_hit_hethn.html %}

Really interesting results can be visualized with the richness feature. Indeed, it appears that the different categories of areas in term of median income per household are quite similarly distributed into the two diversity features. Recalling that a confounder is a variable that influences the two features for which we aim to identify a causality link, causing a wrong association, this is exactly what we observe with the richness feature, which explain why it's of great importance to consider those confounders into the causality analysis.

### Causality between ethnic diversity and food categories purchased diversity
To remove the effect of the confounders and establish a causality link between features, we have used a method called Generalized Propensity Score (GPS) matching. This method allows to compare areas that appear to be quite similar except for the two features for which we aim to determine if a causality link exists. By comparing such areas together, it reduces the effect of the other features (potential confounders) on the causality link we look at. 

Therefore, to determine if some causality exists between the ethnic diversity and the food categories purchased diversity, we used this approach and consider the most correlated features to the food categories purchased diversity as potential confounders. Eventually, to assess the causality between the two features of interest and its significativity, we used a metric based on the 95% confidence interval of the causal curve obtained after the GPS matching. The more positive the feature, the more significant is the causality effect.

The results obtained with this approach suggest that ethnic diversity indeed has an effect on food product categories diversity.

But is it the only feature with such an effect?

Well, to determine this, we performed this process on all the features correlated to the food product categories diversity. The results are displayed in the following table where the features have been ranked by their absolute correlation with the food product categories diversity. The different information present on this table are the name of the features, their correlation value, their causality significance value and their ranking for those different values. The difference in rank is computed by doing the rank of the correlation - the rank of the causality significance. It allows to observe that a high correlation does not necessarily mean that there will be a causality link between the variables. Eventually, the features for which no causal effect have been observed appear in pink.

{% include corr_caus_rank.html %}

These results are quite interesting.

- We can see that the ethnic diversity feature (Ethnic_Group;h_ethnicities_norm;2011) was 9th in the correlation strength rankings and jumps to 3rd in the causal significance ranking.
- The feature representing a very good health for the population in the area (Health;Very_good_or_Good_health_(ratio);2011) loses 42 places and ends up with a negative causality significance metric, which shows that its correlation with the food purchase entropy was actually due to confounders.

Looking at the features we explored with the previous plots we can observe that:

- The richness feature (Household_Income,2011/12;Median_Annual_Household_Income_estimate_(£)) is ranked 10th and then 12th. These results suggest that it has less impact on food purchase diversity than ethnic diversity.
- The age (avg_age) goes from 20th to 7th, suggesting that its effect on food purchase diversity is less affected by confounders than most other features.
- The employment rate (Economic_Activity;Employment_ratio;2011) is ranked 33th and then 27th. It has a significant effect on food product categories diversity but less so than what we initially expected.

### Causality of ethnicities with food categories purchased in Tesco
Now that we have clearly identified that the more diverse the population is (in terms of ethnicity), the more diverse the food purchase will be, let's get down to a finer level of granularity and come back to our main question of interest: Can the prevalence of a certain ethnic group cause a significative effect in purchased product diversity ?

By using the GPS matching, accounting for the potential confounders, we computed the causal significance metric between the different ethnicities and food products categories. 
Those results are represented in the following two graphs with once again two visualizations. One allowing to observe the causality links between a specific ethnicity and all the different product categories and the other allowing to observe what are the ethnicities that have a causal link with the food product chosen. In addition, to the causality significance metric, the correlation values computed previously are reported to observe whether the causality link is positive (cyan) or negative (red) and also to see that a high correlation is not necessary resulting into a high causality significance.

{% include caus_bar_plot_all_items.html %}

{% include caus_bar_plot_all_eth.html %}

Coming back to our three features pairs of interest, what we can conclude following this causality analysis is that:
- The white ethnicity has a causal link with the fraction of food products represented by the ready made meal category. The correlation between those two features being positive, this means that a greater percentage of population from the white ethnic group leads to a higher fraction of ready made meal in the food purchase.

- The black ethnicity has a causal link with the fraction of food products represented by the fruits and vegetables category. The correlation between those two features being negative, this means that a greater percentage of population from the black ethnic group leads to a smaller fraction of fruits and vegetables in the food purchase.

- The asian ethnicity was positively correlated with the percentage of fats and oils purchased. However, no causal link can be identified between those two features meaning that the correlation observed was actually due to confounders.

### Causal curve for some food categories and ethnicities
To observe into details what those causal links look like, we can observe the causal curves resulting from the GPS matching. Those curves allow to observe the direct effect of an increase in a certain ethnic group to the proportion of the food category purchased. The 95% confidence interval is also reported. If an horizontal straight line can be drawn inside this confidence interval, this means that there is no significant causal effect. This is indeed what we can observe when looking at the asian ethnic group with the fats and oils products category.

{% include cdcr_items.html %}

With the results obtained for the white ethnicity and the ready made meals category, we can observe for instance that an increase from 45% to 80% of population from the white ethnic group leads to an increase from 6% to 7% in the proportion of the ready made meal in the food products category purchased in Tesco stores.

## Conclusion - Is your Ethnicity reflected in your Food Purchase?

After a correlation and a causality analysis on the effect of ethnicity on food purchase habits at Tesco in London, we can now answer some key questions: 

- Does ethnic diversity have an effect on food purchase diversity at area level?
- And if yes, what is its nature?
- To which extent are ethnicities responsible for the changes in some product categories purchases? Can we attribute particular food purchase habits to specific ethnic groups?

As we observed a causal effect from the ethnicity diversity in a given area on the food purchase diversity, it suggests that the answer to the first question is yes. The positive correlation result ensures that the causal effect would be positive meaning that when the ethnicity diversity increases, the expected food purchase diversity in the same LSOA increases as well.

Even though we have observed throughout this data story some causal effects of certain ethnicities proportions on certain purchased food categories proportions, we can't fully explain to which extent the causal observations are due to food purchase habits. Indeed, we only have data about Tesco purchases and some people might for example shop at multiple different stores. However, with the tools provided in this data story, you can play with the data and draw conclusions for Tesco customers.

