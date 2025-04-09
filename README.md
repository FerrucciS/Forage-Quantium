![alt text](Images/Quantium.png)

# Retail Customer Insights and Trial Evaluation (Quantium x Forage)


---
## 1. Project Background


A leading supermarket client sought insights into consumer purchasing behaviour within the snack foods category, with a particular focus on potato chips. The objective was to deliver data-driven recommendations to inform an upcoming category review. The analysis was conducted aiming to enhance their understanding of customer purchasing behaviour from July 2018 to June 2019 and evaluate the effectiveness of targeted in-store trials. 


This involved two primary components:
1. **Customer Insights and Segmentation:**
Analysis of transaction and customer data to identify key drivers of chip sales, uncover purchasing trends, and segment customers by value and behaviour. Data preparation included cleaning, merging, and deriving key variables to support actionable insights.
2. **Evaluation of In-Store Trials:**
Selection of control stores and assessment of performance across three trial stores. This phase focused on measuring the impact of strategic in-store initiatives against defined KPIs, using matched controls and pre/post comparisons to determine effectiveness.


The findings from both phases were consolidated into a recommendation for the category team, with a focus on targeting high-value customer segments, optimising product formats, and assessing the commercial viability of scaling the trial initiatives.


---
## 2. Executive Summary

### Part 1: Customer Segmentation Insights

An analysis of 265,000 records from July 2018 to June 2019 shows an annual revenue of approximately $1.8 million from chip sales across 271 stores, with 71,517 loyalty card members. Budget older families are the largest contributors, accounting for 8.7% of total revenue. Their top purchase is Kettle brand chips, spending 48% more on Kettle than the second-most purchased brand, Smiths. They are also 26% more likely to purchase RRD and 18% less likely to purchase Tostitos compared to the general population.


Mainstream young singles/couples are the highest spenders per chip packet, spending an average of $4.05 per packet. Their top brand is also Kettle, where they spend 69% more on Kettle than the second-most purchased brand, Doritos. This group is 23% more likely to purchase Tyrells and 55% less likely to buy Burger Rings compared to the rest of the population. They also tend to prefer larger chip sizes (270g, 380g, 330g), which could indicate they are balancing savings with a preference for premium brands.


To capitalise on key customer segments, the category team should prioritise tailored strategies for both revenue contribution and profitability. For Budget Older Families—who drive the highest total revenue—this includes optimising promotions and shelf placement for Kettle and RRD chips, especially 180g pack sizes. For Mainstream Young Singles/Couples—who spend the most per chip packet—opportunities lie in promoting premium brands like Tyrrells and Kettle, and offering value in larger pack sizes. These targeted actions will help increase sales volume from high-revenue segments and maximise profit margins from high-spend-per-unit customers.


### Part 2: Trial Store Impact Summary

The trial period led to a measurable uplift in performance for stores 77 and 88, though through different mechanisms. Store 77 saw a significant increase in monthly customer count, indicating the trial attracted new shoppers. In contrast, store 88 showed a significant rise in transactions per customer, suggesting improved engagement from existing customers. Store 86, however, showed no significant difference compared to its control, indicating limited trial impact. These results support the trial's effectiveness overall and highlight store-specific strategies worth investigating further.



---
## 3. Data Overview

![alt text](Images/ERD1.png)

The dataset includes transaction records and customer behavior details across multiple stores. The data spans a variety of customers, providing valuable insights into purchasing behavior and demographics. To prepare the dataset for analysis, several steps were undertaken to ensure its integrity and usability:


1. Handling Missing Values: Missing data was either imputed or removed to ensure consistency and completeness.
2. Outlier Detection: Identified and addressed outliers to avoid distortion in analysis.
3. Feature Engineering: Additional features, such as pack size, were derived to enhance the analysis.
4. Data Type Conversion: Corrected data formats, such as converting dates from strings to datetime objects for proper analysis.
5. Categorical Transformation: Some string columns, including lifestage and premium_customer, were converted to categorical variables to optimize performance and memory usage.


These transformations ensure that the dataset is well-structured and ready for comprehensive analysis, allowing for deeper insights into customer behavior and purchase patterns.



---
## 4. Key Insights Deep Dive


## Part 1: Customer Segmentation Insights


### Overview of Customer Segmentation

Customers were segmentated using two attributes
- LIFESTAGE: Customer attribute that identifies whether a customer has a family or not and what point in life they are at e.g. are their children in pre-school/primary/secondary school.
- PREMIUM_CUSTOMER: Customer segmentation used to differentiate shoppers by the price point of products they buy and the types of products they buy. It is used to identify whether customers may spend more for quality or brand or whether they will purchase the cheapest options.

These attributes lead to the following segmentation:
| LIFESTAGE    | 
|--------------|
| Midage singles/couples |
| New families           |
| Older families         |
| Older singles/couples  |
| Retirees               |
| Young families         |
| Young singles/couples  |

| PREMIUM_CUSTOMER | 
|------------------|
| Budget           |
|Mainstream        |
|Premium           | 


The population distribution is as follows:
- Budget older families are the largest customer segment, accounting for 8.7% of the total population.
- Premium new families are the smallest customer segment, accounting for 0.6% of the total population.

![distribution table](Images/Segmentation.png)
  



### Revenue Contribution by Segment

This section examines the revenue contribution from each LIFESTAGE and PREMIUM_CUSTOMER segment. By analyzing these segments, we can identify the groups driving the most sales and understand where focus should be placed to maximize revenue.

- Total revenue is $1,819,778.
- _**Budget older families**_ account for the largest percentage of total sales - 8.7%, contributing $158,380 to the yearly revenue.
- Mainstream young singles/couples and mainstream retirees are second and third, making up 8.2% and 8.0% of total revenue respectively.


![alt text](Images/Tot_sales.png)


**Favorite Chip Brand for Top Contributor**

- Kettle brand drives the biggest sales for budget older families.
- Budget older families spend 48% more on Kettle brand than the second most purchased brand, Smiths.


![alt text](Images/fav_brand.png)


**Brand and Size Preferences Relative to Population**

This section examines the brand and size preferences of budget older families in comparison to the general customer population. To identify which brands and sizes budget older families are more likely to purchase, we calculated the relative preference for each product based on the frequency and volume of their purchases.

- Budget older families are 39% more likely to purchase 180g packet sizes.
- Budget older families are 11% less likely to purchase 134g packet sizes.
- On average, this segment shows more of an inclination towards smaller pack sizes, suggesting they may prioritize more convenient or affordable options.


Grain Waves and Pringles are the only brands that offer 180g and 134g packets respectively. These size preferences might therefore reflect a higher or lower likelihood to purchase these specific brands. We will see if this is the case below.

<img src="Images/size_pref.png" width="750" height="750">



The brands that that budget older families are most and least likely to purchase include:
- RRD 26% more likely.
- Tostitos 18% less likely.


Taking into account the size preferences we observe:

- Regardless of size Pringles in general are 11% less likely to be purchased.
- Grain Waves in general are purchased at roughly the same likelyhood as the rest of the population. It is only the smaller, 180g, Grain Waves packets which they tend to purchase more relative the rest of the population.


This again indicates a preference for smaller, more affordable packs, which could align with the budget-conscious nature of this segment.


<img src="Images/brand_pref.png" width="750" height="750">

---

### Profitability Contribution by Segment


This section examines the revenue contribution from each LIFESTAGE and PREMIUM_CUSTOMER segment, focusing on the groups that spend the most on average per chip packet. By identifying these segments, we can better understand where to focus efforts to maximize profit.


- Mainstream young singles/couple spend $4.05 per pack.
- Mainstream midage singles/couple spend $3.98 per pack
- Premium retirees spend $3.91 per pack.
- Budget young singles/couples spend the least at $3.64 per pack.

A t-test confirmed significant differences among the top three spenders, adding credibility to these insights.


<img src="Images/high_paying.png" width="750" height="750">


**Favorite Chip Brand for Top Contributors**

- All three highest-paying segments purchase Kettle the most, followed by Dorito
- Mainstream young singles/couples spend 69% more on Kettle than on Doritos, showing a strong brand preference.


![high](Images/higest_paying_brand.png)


**Brand and Size Preferences Relative to Population**


This section explores the brand and size preferences of the highest-spending segment — mainstream young singles/couples — in comparison to the overall customer population. To identify which products this group is more or less likely to purchase, we calculated the relative preference for each product based on the frequency and volume of their purchases.


 - They are 27% more likely to purchase 270g packs and 25% more likely to purchase 380g packs.
 - They are 55% less likely to purchase 220g packs and 51% less likely to purchase 70g packs.
 - Overall, this segment shows a clear preference for larger pack sizes, suggesting a tendency toward bulk buying or value-driven shopping.

It's worth noting that Twisties and Burger Rings are the only brands offering the 270g and 220g sizes, respectively. Therefore, to accurately interpret these size preferences, we also need to consider this segment's brand preferences — as the trend may reflect brand affinity rather than size alone.


<img src="Images/Pack_size_top_spender.png" width="750" height="750">


The brands that mainstream young singles/couples are most and least likely to purchase include:

- Tyrells are 23% more likely to be purchased.
- Burger Rings are 55% less likely to be purchased..


When considering size preferences alongside brand choices, we observe:


- Burger Rings are only available in 220g packs — a size this segment is significantly less likely to purchase. This suggests the low preference is driven by brand, not just pack size.
- Twisties are the second most preferred brand among this group, and they are the only brand offering 270g packs. This reinforces the idea that the preference for 270g sizes may reflect a strong brand preference for Twisties rather than size alone.


<img src="Images/brand_top_spender.png" width="750" height="750">








## Part 2: Trial Store Analysis



The Category Manager for chips has asked us to test the impact of the new trial layouts with a data driven recommendation to whether or not the trial layout should be rolled out to all their stores. Here, we will ecaluate the performance of a store trial which was performed in stores 77, 86 and 88 over the period 01-Feb-2019 - 30-Apr-2019.


### Selcting Control Stores


**Define Metric**


### Assessment of the Trial


**Total Monthly Sales**



**Monthly Customers**



**Monthly Transactions per Customer**














---
## 5. Recommendations

**To increase revenue and cater to Budget Older Families:**
- Focus on promotions for larger, premium-sized packets like Grain Waves and Kettle, which align with this segment’s preferences.
- Highlight value for money in premium products to attract this high-contribution segment.


**To maximize profits with Mainstream Young Singles/Couples:**
- Promote larger pack sizes of popular brands like Smiths, Twisties, Cheezels, and Doritos while maintaining a strong focus on premium brands like Kettle and Tyrells.
- Create bundles or discounts on larger pack sizes to further incentivize purchases.



---
## 6. Clarifying Questions, Assumptions & Caveats

