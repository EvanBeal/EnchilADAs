---
layout: page
title: Is your Ethnicity reflected in your Food Purchase?
cover-img: "/assets/img/fish_chips.jpg"
subtitle: Analysis of Tesco and socio-economic data of Londoners
---

## London, a city of diversity
London is one of the most populated cities in Europe. With almost 9 millions of inhabitants, the population comes from all walks of life. Therefore, a great heterogeneity appears between the Londoners, which can be mirrored at the level of their age, financial means or origins and ethnicities for instance.

This heterogeneity can be pictured with the different areas of the city. Indeed, living close to Buckingham Palace and being in daily contact with the Queen and the Prime Minister  is only accessible to a population with really significant financial means, resulting in less heterogeneity in this district from an economic viewpoint. In contrary, we can easily imagine that living in the suburbs offer some great advantages to a wide range of people, resulting in areas with really diverse inhabitants. 

To determine whether our ethnicity is one of the factor that could influence our food purchase, we would like to capture this heterogeneity present in the different areas of the city. Therefore, the analysis has to be done at the area level and many possibilities appear to subdivide London into different districts. One can consider the 32 Boroughs for example. However, those areas are very large (from 150k to 300k inhabitants) and may not be really representative of everyone's diversity. That's why we decided to conduct our analysis at the Lower Super Output Area (LSOA) level, the finest subdivision of the city possible. Those 4'833 areas have an average population smaller than 2k and therefore offer a great resolution to link the food purchase to the diversity of the Londoners. 

## Tesco, "Every little helps"  
With this slogan, Tesco wants to be close to the population. This is one of the reason that allowed this British groceries and general merchandise retailer to become a multinational and the market leader of groceries in UK with more than a quarter of the market share. This position of leader renders the data of its customer really valuable to link food purchases to a number of socio-economic factors. That's why the Tesco Grocery 1.0 dataset, a record of the food items purchased by 1.6 M Tesco customers, came out with a great interest to perform multiple studies. 

This dataset has been proven to be ecologically valid by comparing the food purchases with metabolic syndrome conditions that are strongly linked to food consumption habits, in the paper ["Tesco Grocery 1.0, a large-scale dataset of grocery purchases in London"](https://www.nature.com/articles/s41597-020-0397-7). Therefore, we will use some features of this dataset (the fractions of food product categories, per area) to identify whether the food basket of the Tesco customers is the reflect of their ethnicity.

## How can we determine the effect of ethnicity on food purchase?
Our main question of interest being to find out whether our roots influenced our way of shopping in Tesco stores, two main analyses have to be performed in order to identify potential **correlation** and **causality** between the ethnicity and the food items purchased. That's why, throughout this datastory, you will have the opportunity to observe the links between the different combination of ethnicities and food categories purchased, guided by the main results we obtained, in order to establish whether some food purchase patterns that appear to be specific of a certain ethnicity.  

## Correlation analysis
### Correlation of ethnicities with food categories purchased in Tesco

### First look of the correlation between the items bought in Tesco stores and the ethnicities of the different area
{% include corr_bar_plot_all_items.html %}

{% include corr_bar_plot_all_eth.html %}

It appears that indeed the items bought in Tesco store may depend on your ethnicity. 

### Map visualization of the correlation
This is something that we can also try to assess visually using the following two maps representing the ethnicities of the Londoners and their food consumption.
You can try to look at the correlated combination and see if it shows some visual correspondance on the maps. 

#### Food Purchase in London
{% include map_food_small.html %} 

#### Ethnic groups in London
{% include map_ethnicity_small.html %}

However, to determine if there is a real effect, it's really not enough to consider only this correlation study and the visualization. 
A more complex study should be performed considering other socio-economic factors. 
To do so, we had to reunite the information of the different ethnicities into one feature representing the ethnicity diversity of the area.
The same has to be done with the items bought to Tesco resulting to a feature of diversity of food purchase.

## Causality analysis 

### Which factors may also be linked to the diversity of food purchase?
Many factors in addition to your ethnicity may be linked in fact to your food habits. We can mention for instance, your age, your salary, whether or not you have a job or whether or not you are in good health. These factors have to be considered in our study to not draw causal links that may have been explained in fact by one of those factors.

### How richness, employment rate and the average age of the area are linked to diversity of food consumption and ethnicity?

#### Linear Regression
{% include reg_plot.html %}

#### How those features are linked together
{% include rich_employ_age_hit_hethn.html %}

### Causality of ethnicities with food categories purchased in Tesco
{% include corr_caus_rank.html %}

{% include caus_bar_plot_all_items.html %}

{% include caus_bar_plot_all_eth.html %}

### Causal curve for some Tesco items
{% include cdcr_items.html %}

## Conclusion

## Limitations



