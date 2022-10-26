# customer-segmentation-DS007  
### Data science project for finding meaningful customer segmentation and recommendations are given  


---  
<br>  

## <div id='executive'>A. Executive Summary</div>  
For a better target marketing campaign, a customer segmentation analysis revealed there are 3 major customer segments (93% of customers). Each cluster has unique behaviors shown below:  
- Overall, they purchase wine, meat, and fish from store. Target marketing strategies that are suitable from this condition could be applied (e.g. marketing campaign focussing on offline instead of online campaign)  

To be specific:  
**Cluster 3** (20% of customers),  
- ___The purchase behavior___: middle high income, purchase in very high quantity from store (high quantity errand), wines lover, meat lover  
- ___The strategy___: premium membership (make sure they come back for the next errand), discount for high quantity volume product, marketing campaign in store, product stock strategies in errand weeks   
  
**Cluster 2** (48% of customers),  
- ___The purchase behavior___: middle low income, purchase in very low quantity from store, the purchased products are so diverse  
- ___The strategy___: marketing campaign in store  
  
**Cluster 0** (25% of customers),  
- ___The purchase behavior___: middle income, purchase in high quantity from store (high quantity errand), wines lover  
- ___The strategy___: premium membership (make sure they come back for the next errand), discount for high quantity volume product, marketing campaign in store, product stock strategies in errand weeks  


---  
<br>  

## <div id='contents'>B. Contents</div>  
[A. Executive Summary](#executive)    
[B. Contents](#contents)    
[C. Planning](#planning)    
[D. Analysis & Finding](#finding)         


---  
<br>  

## <div id='planning'>C. Planning</div>  

### 1. Business Needs
> ***How would you as a Data Scientist find meaningful segmentations of this market place?***  

<br>
I would assume about this problem that:
- This research is trying to find customer segmentations for marketing purposes.  
- From all of users in given dataset, I would use all the user w/o any filtering specific attributes of the users.  

At the end of this research, the outcomes are:
- number of segmentations found
- description of unique attributes from each segment
- business recommendations for each segment  
<br>  

### 2. Business Process  
From the dataset, the business is an online & offline market place.  


So, the business process or users funnel in online setting, I assume it would be like:
1. Customers visit the market place's website
2. Customers may sign up and then fill in their personal information (perhaps the customers not sign up, so we don't obtain the personal information)    
3. Customers make some purchases through search engine (it may be not through search engine)
4. Customers receive the purchased items  

Then, the business process or users funnel in offline store, I assume it would be like:  
1. Customers visit the market place's stores
2. Customers select one of items to be purchased
3. Customers make a purchase
4. Customers leave the store
<br>  

### 3. Business Requirements  
**a. The research timing**  
From the dataset, I assumed that the research is held after some periods of time (maybe 1 month) because after look up to the dataset, the data given is aggregated. Then, I would conclude that this research is held to give updated information about customer segmentation for each month. Because of this updated information, the marketing team would be always well informed about the behaviour of customers and could make a better target marketing.   

**b. The research frequency**  
From my conclusion above in the `a. The research timing`, I make another conclusion that this research runs montly basis.  

<br>  

### 4. Data Source  
The dataset is from Kaggle, uploaded by [Akash Patel](https://www.kaggle.com/datasets/imakash3011/customer-personality-analysis), provided by Dr. Omar Romero-Hernandez.  
The description for the dataset's columns: 


***People***  
`ID`: Customer's unique identifier  
`Year_Birth`: Customer's birth year  
`Education`: Customer's education level  
`Marital_Status`: Customer's marital status  
`Income`: Customer's yearly household income  
`Kidhome`: Number of children in customer's household  
`Teenhome`: Number of teenagers in customer's household  
`Dt_Customer`: Date of customer's enrollment with the company  
`Recency`: Number of days since customer's last purchase  
`Complain`: 1 if the customer complained in the last 2 years, 0 otherwise  

***Products***  
`MntWines`: Amount spent on wine in last 2 years  
`MntFruits`: Amount spent on fruits in last 2 years  
`MntMeatProducts`: Amount spent on meat in last 2 years  
`MntFishProducts`: Amount spent on fish in last 2 years  
`MntSweetProducts`: Amount spent on sweets in last 2 years  
`MntGoldProds`: Amount spent on gold in last 2 years  

***Promotion***  
`NumDealsPurchases`: Number of purchases made with a discount  
`AcceptedCmp1`: 1 if customer accepted the offer in the 1st campaign, 0 otherwise  
`AcceptedCmp2`: 1 if customer accepted the offer in the 2nd campaign, 0 otherwise  
`AcceptedCmp3`: 1 if customer accepted the offer in the 3rd campaign, 0 otherwise  
`AcceptedCmp4`: 1 if customer accepted the offer in the 4th campaign, 0 otherwise  
`AcceptedCmp5`: 1 if customer accepted the offer in the 5th campaign, 0 otherwise  
`Response`: 1 if customer accepted the offer in the last campaign, 0 otherwise  

***Place***  
`NumWebPurchases`: Number of purchases made through the company’s website  
`NumCatalogPurchases`: Number of purchases made using a catalogue  
`NumStorePurchases`: Number of purchases made directly in stores  
`NumWebVisitsMonth`: Number of visits to company’s website in the last month  


---  
<br>  

## <div id='finding'>D. Analysis & Finding</div>    

### 1. Exploratory Data Analysis  
1.1. Data Structure (shape, datatype, number of samples, univariate stats, multivariate stats)    
1.2. Quality Investigation (duplication check, missing values check, outliers check, unwanted entries check)  
1.3. Content (correlation analysis, data visualisation)  

### 2. Data Preprocessing  
2.1. Data Cleaning (remove or imputation)  

### 3. Feature Engineering  
3.1. Poeple related: `age`, `is_parent`, `tot_teen_kid`, `edu_num_encode`, `tot_prod_of_edu` (in avg, std, max, min), `tot_prod_of_marital` (in avg, std, max, min), `income_per_age`, date decomposition into (`year`, `month`, `date`, `day`, `is_weekend`, `is_customer_for_day`)  

3.2. Product related: `tot_prod`, `avg_prod`, `wines_per_day`, `fruit_per_day`, `meat_per_day`, `fish_per_day`, `gold_per_day`, `sweet_per_day`    

3.3. Promotion related: `tot_accepted_cmp`, `num_deal_per_tot_purchased`, `avg_accepted_cmp`, `std_accepted_cmp`, `tot_prod_per_num_deals`, `avg_prod_per_num_deals`  

3.4. Place related:`tot_num_purchased`  


### 4. Feature Selection  
4.1. Principal Component Analysis (PCA) - for dimensionality reduction to address the curse of dimensionality  

### 5. Model  
5.1. K-Means Clustering Method  
5.2. Elbow Methods: I found 5 meaningful clusters here.  

### 6. Evaluation  
6.1. Descriptive statistics.  

### 7. Conclusion  
After done the data preparation process, feature engineering, then feature selection with PCA method, I used K-Means method for clustering analysis and also an elbow method to find the good numbe of cluster. The elbow method showed that 5 cluster is good number for cluster found in the dataset.  

From the cluster information, I did a correlation analysis and then selected which columns that have medium to strong correlation to cluster and also ease to interpret. Finally I did some descriptive analysis to extract useful information.  

the new meaningful information we could extract:

**Population of Customer**  
- 93,..% customers come from cluster 3 (20%), 2(48%), 0(25%)  
- almost 50% customers, they come from cluster 2  
- I decided later focussing on cluster 0, 2, and 3 only  

**Demographic of cluster 1, 2, 3**  
- cluster 3 - middle high income, not a parent, no teen  
- cluster 2 - middle low income, a parent, no teen  
- cluster 0 - middle income, a parent, have one teen  

**Promotion of cluster 1, 2, 3**  
The average accepted campaign is 5% or less for cluster 0, 2, 3. It is too low.  

**Place of purchase of cluster 1, 2, 3**  
- cluster 3 - mostly purchase from store (44% out of time), then catalog(30%)  
- cluster 2 - mostly purchase from store (55% out of time), then web(36%)  
- cluster 0 - mostly purchase from store (45% out of time), then web(36%)  

**Purchase of cluster 1,2,3**  
the customer mostly purchase wine, meat, & fish. I concluded that the customers mostly are parent or adults  

- cluster 3 - medium number of customer, purchase in very high quantity of products, wines lover - always buy one wine per person, meat lover - always buy one meat, 21% out of time purchase fist  
- cluster 2 - high number of customer, purchase in low quantity, the purchased types of product are so diverse  
- cluster 0 - medium number of customer, purchase in high quantity of products, wine lover - 70% out of time purchase wine, 22% out of time purchase meat  

At the early stage of planning, the `3. Business Requirement` require us to do clustering analysis, so the marketing team is always well informed and also could make a better target marketing.  

Following the extracted information above, the recommendation and action that could follow this analysis would be:  
- If I used total revenue generated or total product purchased as a primary metric, focussing only to cluster 0, 2, and 3 is a wise choice
- Customer from cluster 0, 2, 3 mostly purchase wine, meat, and fish from store. Target marketing strategies that are suitable from this condition could be applied (e.g. marketing campaign focussing on offline instead of online)  

To be specific:  
**Cluster 3** (20% of customers),  
- ___The purchase behavior___: middle high income, purchase in very high quantity from store (high quantity errand), wines lover, meat lover  
- ___The strategy___: premium membership (make sure they come back for the next errand), discount for high quantity volume product, marketing campaign in store, product stock strategies in errand weeks   
  
**Cluster 2** (48% of customers),  
- ___The purchase behavior___: middle low income, purchase in very low quantity from store, the purchased products are so diverse  
- ___The strategy___: marketing campaign in store  
  
**Cluster 0** (25% of customers),  
- ___The purchase behavior___: middle income, purchase in high quantity from store (high quantity errand), wines lover  
- ___The strategy___: premium membership (make sure they come back for the next errand), discount for high quantity volume product, marketing campaign in store, product stock strategies in errand weeks  
