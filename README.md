Introducing the problem: 
This project aims to analyze customer credit card usage patterns using clustering techniques. The objective is to segment customers based on their spending behavior and credit card usage, enabling better customer services and targeted services. The questions to address are: 
Can we identify distinct customer groups based on their credit card usage? 
What insights can we draw about the spending behaviors of these groups?
What are the characteristics of high-value customers? 
How can these segments inform marketing strategies?
What is Clustering and how does it work?
Clustering is an unsupervised machine learning technique used to group data points into clusters such that data points in the same cluster are more similar to each other than to those in other clusters. It helps in identifying hidden patterns or groupings in data.
Techniques: 
K-Means: Divides data into kkk clusters by minimizing within-cluster variance.
Hierarchical Clustering: Iteratively merges data points into clusters based on proximity.
Introduce the data: 
My dataset is sourced from kaggle. The dataset includes anonymous credit card usage data. 
Link to dataset: https://www.kaggle.com/datasets/arjunbhasin2013/ccdata
Some of the features are: 
Balance: Average balance.
Purchases: Total purchase amount.
CashAdvance: Cash withdrawn using the card.
CreditLimit: Customer’s credit limit.
PURCHASES_FREQUENCY : How frequently the Purchases are being made, score between 0 and 1 (1 = frequently purchased, 0 = not frequently purchased)
ONEOFFPURCHASESFREQUENCY : How frequently Purchases are happening in one-go (1 = frequently purchased, 0 = not frequently purchased)
PURCHASESINSTALLMENTSFREQUENCY : How frequently purchases in installments are being done (1 = frequently done, 0 = not frequently done)
Data Visualization: 
To better understand the data and features, I have created two visualizations so far although I intend to create more visualizations in my final draft. 
Relationship between balance and purchases 
I visualized the correlation between balance and the number of purchases to see how a customer’s balance influences their purchasing behavior. This visualization helped me notice trends and outliers, providing a clear understanding of how balance interacts with the purchases feature. 
Distribution of balance
I plotted the distribution of balance to observe its variability and range. This visualization revealed a skewed distribution, suggesting the presence of outliers or potential clusters in the data although it makes sense that people with a lower balance make more purchases. 
Key Insights:
Customers with extremely high balances appear to exhibit distinct purchasing patterns, which could influence how features are weighted during modeling. Customers with higher balances might also have higher credit limits. 
The skewness in the balance distribution suggests that scaling or transformation might be necessary to normalize the data for clustering or predictive analysis.
How it helps modeling: 
These visualizations ensure that key features like balance are well understood before modeling. Identifying trends, outliers, and patterns supports better feature engineering and preprocessing, ultimately leading to more accurate and interpretable models. 





Pre-Processing: 
Handling Missing Values:
Rows with null values in the credit limit and minimum payment columns were processed by replacing the null values with the mean. This ensured that missing data did not skew the results.
Column Removal:
I removed the CUST_ID column as it is a unique identifier and does not contribute to clustering analysis. Additionally, it was an object-type value, which is unnecessary for this task.


Modeling(Clustering): 
I chose to do the k-means clustering model for my project because it is efficient and scalable for larger datasets such as mine which includes credit card transaction data. It is simple and outputs cluster centroids which was suitable for my dataset to understand customer segmentation (average balance or purchase frequency per cluster). 
Implementation: 

Storytelling(Clustering Analysis):
The clustering of credit card data provided meaningful insights about the dataset. I have answers towards all my 
Cluster 0: Moderate spenders 
Cluster 1: Low spenders with minimal credit usage 
Cluster 2: High spenders and premium customers 
Insights: 
Cluster 0 are moderate spenders who often utilize installment purchases, potentially indicating financial instability. 
Cluster 1 are low spenders with minimal credit usage. Customers in this cluster would not be profitable and represent low-value customers in terms of spending. The cluster may consist of people who are new to using credit cards, people with low budgets, or people who do not rely heavily on credit. Banks could target this group with cashback or introductory offers to increase spending. 
Cluster 2: 
This cluster represents high-value customers who make the most frequent and largest purchases while also maintaining a good payment history. This cluster represents the most profitable group for the business. Companies could retain these customers with exclusive perks like travel rewards. 
I was able to answer my initial questions that I had at the start. 
Can we identify distinct customer groups based on their credit card usage?
Yes, clustering analysis segmented customers into three distinct groups based on their spending, payment, and credit usage patterns.
What insights can we draw about the spending behaviors of these groups?
The analysis revealed varying behaviors, such as moderate spenders using cash advances, low spenders underutilizing credit, and high-value customers with frequent and high-volume purchases.
What are the characteristics of high-value customers?
High-value customers exhibit high purchases,  frequent transactions, a tendency to pay balances in full, and significantly higher credit limits. 
How can these segments inform marketing strategies?
These segments enable targeted strategies, such as offering rewards to high-value customers, incentivizing low spenders to increase engagement, and educating moderate spenders on balance management.
Cell Output: 
 
Impact Section: 
Potential positive impacts: 
Enhanced Customer Experience:
By tailoring marketing strategies to specific customer segments, businesses can provide personalized offers, improve customer satisfaction, and foster loyalty.
Improved Business Profitability:
Identifying high-value customers allows businesses to focus resources on their most profitable segments, increasing return on investment.
Financial Inclusion:
Strategies targeting low-spending customers can encourage better credit utilization, potentially improving their financial literacy and inclusion.

Potential Negative Impacts:
Privacy Concerns:
Using customer financial data for clustering might raise ethical concerns if customers are unaware or if the data is not handled securely.
Unintended Bias:
Segmentation could inadvertently lead to biased treatment of certain groups, such as offering fewer benefits to low-income customers, perpetuating inequality.
Over-Targeting:
Aggressive marketing to specific segments could lead to customer dissatisfaction or even churn if perceived as intrusive.
Overall, while this project can significantly improve customer engagement and profitability, it requires careful consideration of ethical and social implications to balance business goals with customer trust and equity.

References: 
Pizza Hut clustering notebook from canvas 
https://www.geeksforgeeks.org/k-means-clustering-introduction/
Code: 
On Github
