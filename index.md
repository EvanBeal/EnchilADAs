---
layout: page
title: Is your Ethnicity reflected in your Food Purchase?
cover-img: "/assets/img/fish_chips.jpg"
subtitle: Analysis of Tesco and socio-economic data of Londoners
---

- Does ethnic diversity have an effect on food consumption at area level? 
- And if yes, what is its nature? 
- To which extent is the ethnic diversity responsible for the food consumption diversity of some aliment categories? 
- Can we attribute particular food habits to specific ethnic groups?

## Story Plan

### Introduction
- Speak about the data considered
- How we get to this problematic 
- How we will try to determine if it's really the case 

### First look of the correlation between the items bought in Tesco stores and the ethnicities of the different area
- heatmap of the correlation of items vs ethnicities 
- OR barplot of correlation with the ethnicities on x-axis and the items as slide bar or dropdown menu (or the opposite) 
{% include corr_bar_plot_all_items.html %}

{% include corr_bar_plot_all_eth.html %}

It appears that indeed the items bought in Tesco store may depend on your ethnicity. 

### Visualization of the correlation
This is something that we can also try to assess visually using the following two maps representing the ethnicities of the Londoners and their food consumption.
You can try to look at the correlated combination and see if it shows some visual correspondance on the maps. 

#### Food consumption in London
{% include map_food.html %} {% include map_ethnicity.html %}

#### Ethnic groups in London


However, to determine if there is a real effect, it's really not enough to consider only this correlation study and the visualization. 
A more complex study should be performed considering other socio-economic factors. 
To do so, we had to reunite the information of the different ethnicities into one feature representing the ethnicity diversity of the area.
The same has to be done with the items bought to Tesco resulting to a feature of diversity of food consumption.

#### Ethnicity and Food consumption diversity
- map with those two features or put those features on the previous maps

### Which factors may also be linked to the diversity of food consumption?
Many factors in addition to your ethnicity may be linked in fact to your food habits. We can mention for instance, your age, your salary, whether or not you have a job or whether or not you are in good health. These factors have to be considered in our study to not draw causal links that may have been explained in fact by one of those factors.

#### Socio-economic factors
{% include map_socio_eco.html %}

### How richness, employment rate and the average age of the area are linked to diversity of food consumption and ethnicity?

#### Linear Regression
{% include reg_plot.html %}

#### How those features are linked together
{% include rich_employ_age_hit_hethn.html %}

### Causality analysis 
{% include corr_caus_rank.html %}

The richer you are the less diverse you eat? Let us doubt about it.
This may have something to do with the **representativeness** of the Tesco data. Indeed, they may be the leader for groceries in UK, they still don't have the food market monopoly.
Of course, on one hand we want the Tesco data to be as representative as possible than the food consumption of the Londoners. However, on the other hand we also want to have enough areas to consider in the study to obtain results with a greater power. 
We decided to take into account areas that have a representativeness higher than XXX.

#### Visualization of how the representativeness affects the linear relation between the diversity of food consumption and ethnicity
- Scatter plot with a slide bar for representativeness ?

### Linear relation of the features with the diversity of food consumption
- Plot of the linear regression with the different features (may be variance explained that grows when adding some features)

Conclusion: the more diverse in ehtnicity the area is, the more diverse the food consumption will be? We still don't know !
Indeed, many other socio-economic factors are also showing some significant linear relation with the food consumption diversity. We need to consider the effect of those potential confounders. 

### Propensity score
Determine a threshold to separate the areas into two groups based on their diversity in food consumption.
Computation of a propensity score to match corresponding areas and decrease the effects of the other socio-economic factors.

- Plot of the distributions before and after matching (with side bar or button to select the feature to observe)
- Plot showing the matching areas with a text box giving the main information OR somehow a scatter of propensity vs features with 4 colors (combinations, treated or not, matched or not)

### Conclusion

### Limitations

### Additional observations (fun facts)
Performing a similar analysis which other effects have been observed


