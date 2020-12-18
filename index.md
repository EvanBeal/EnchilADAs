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

This dataset has been proven to be ecologically valid by comparing the food purchases with metabolic syndrome conditions that are strongly linked to food consumption habits, in the paper ["Tesco Grocery 1.0, a large-scale dataset of grocery purchases in London"](https://www.nature.com/articles/s41597-020-0397-7). We extend it with the [LSOA atlas](https://data.london.gov.uk/dataset/lsoa-atlas), an official dataset reporting census data at LSOA level, which gives us information on the distributions of different ethnic groups accross London. Using both those sources, we will try to see if the prevalence of different ethnic groups have an impact on the content of the food basket of Tesco's customer.

## How can we determine the effect of ethnicity on food purchase?
Our main question of interest being to find out whether the appartenance of customer to a certain ethnic group influence their way of shopping in Tesco stores, two main analyses have to be performed in order to identify potential **correlation** and **causality** between the ethnicity and the food products purchased. 

Throughout this datastory, you will have the opportunity to observe the links between different combination of ethnic groups prevalence and food categories purchased, guided by the main results we obtained, in order to establish some food purchase patterns that appear to be specific of certain ethnic groups. 

Following the common thread of our analysis based on the following pairs of features:
- White ethnic group and ready made food category
- Black ethnic group and fruits & vegetables food category
- Asian ethnic group and fats oils food category
you will be able to draw your own conclusion on the examples that spark your curiosity.

## Correlation analysis
### Correlation of ethnicities with food categories purchased in Tesco
To begin our analysis, we want to see if there are some relations between the different product categories and the ethnic groups. A simple approach to look if some relations exist between two features is to look at their correlation. Indeed, if there is no correlation between them, we can't expect any causal relations to be present. Therefore, with this first outlook, we get an idea on a potential reflect of the ethnicity on food purchase and even more precisely if there is some postive or negative links between the ethnicities and the food categories purchased in Tesco. 

### First look of the correlation between the items bought in Tesco stores and the ethnicities of the different area
Those two first figures allow to visualize how the prevalence of certain ethnic groups correlate with the probability of certain products categories to appear in a typical shopping cart. The two visualizations allow to look at those data from different points of view:
- How does the prevalence of a specific ethnic group correlate with the prevalence of the different product categories ?
{% include corr_bar_plot_all_items.html %}

- How does the prevalence of a specific product category is correlated with the prevalences of the different ethnic groups ?
{% include corr_bar_plot_all_eth.html %}

We can indeed see that the composition of the typical shopping cart is linked with how much certain ethnic groups are represented in the area where the purchases are carried. Looking at our three features pairs of interest, what we can conclude from those plots is that:
- The white ethnicity is positively correlated with the fraction of food products represented by the ready made meal category. This means that the more the white ethnicity is represented in an area the more important the place of the ready made meal will be in the shopping cart of the Tesco customers. 
- The black ethnicity is negatively correlated with the fraction of fruits and vegetables. The percentage of fruits and vegetables in the food products purchased decreases the more the black ethnicity is represented in an area.
- The asian ethnicity is positively correlated with the percentage of fats and oils purchased, indicating that a higher representativity of the asian ethnicity in an area will lead to a greater purchase of fats and oils in comparison to the other food products categories. 

### Map visualization of the correlation
We can also try to assess the correlation visually by comparing how the ethnicities are represented in the different areas of London and how the fraction of products category purchased vary on maps of the London LSOA. 
You can try to look at some combinations of the correlated features and see if visually you can identify those positive or negative correlations. 

#### Food Purchase in London
{% include map_food_small.html %} 

#### Ethnic groups in London
{% include map_ethnicity_small.html %}

Considering the white ethnicity and the fraction ready made meals, the positive correlation can be indeed well observed. It appears that the fraction of read made meals purchased in Tesco increases the further away from the center of London you go, especially in the South and East suburbs where we can also observe areas with a high percentage of population having a white ethnicity.

However, to determine if there is a real causality effect and being able to establish whether our ethnicity is really reflected in some of the products categories we purchased, it's really not enough to consider only this correlation study and the visualization. 
A more complex study should be performed considering other socio-economic factors that may also be correlated with the categories of products bought in Tesco. 

## Causality analysis 
To do so, we had to reunite the information of the different ethnicities into one feature representing the ethnicity diversity of the area.
The same has to be done with the items bought to Tesco resulting to a feature of diversity of food purchase.

### Which factors may also be linked to the diversity of food purchase?
Many factors in addition to the appartenance to a specific ethnic group may be linked in fact to your food habits. We can mention for instance, your age, your salary, whether or not you have a job or whether or not you are in good health. These factors have to be considered in our study to not draw causal links that may have been explained in fact by one of those factors.

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

## Fun facts
Is the cliché of the British drinking its cup of tea only a cliché ?!? Naaa, it's just probably that Tesco has not the right standing to be involved in this art.



