# Group17MLProject

Hi everyone! This is the link to our Machine Learning Project Github Pages.
https://github.gatech.edu/pages/sdesai328/Group17MLProject/

Proposal Video: [Link](https://www.youtube.com/watch?v=OQ27c0DZCqA)


## Part 1: Literature Review and Dataset

In today’s economy, where the market seems very volatile due to inflation and uncertainty, gold
is becoming an increasingly important asset. Being able to retain its value over time, gold is able
to hedge against this volatility making it important for investors to have accurate price
forecasting. Recent studies have explored various machine learning techniques to improve
prediction accuracy. For example, Ghule and Gadhave [1] applied Random Forest regression to
predict future gold rates, illustrating the model’s ability to capture patterns in gold price
movements. In addition, Alharbi [2] also looked into predicting precious metal prices using
machine learning methods from 2017 to 2023, providing insights into the market and predictive
modeling. Finally, Zainal and Mustaffa [3] conducted a literature review on gold price
forecasting techniques, emphasizing the evolution from traditional statistical methods to
advanced machine learning approaches. Their work shows the potential of using multiple
methods to try and forecast the nonlinear dynamics of gold prices which we look to explore.

### Datasets

- a. Historical gold data: [Yahoo Finance](https://finance.yahoo.com/quote/GC=F/)
- b. Economic indicators like inflation, interest rates, GDP growth, and foreign exchange rates [4]: [FRED](https://fred.stlouisfed.org/)
- c. Exchange rates: [IMF](https://www.imf.org/external/np/fin/data/param_rms_mth.aspx)

## Part 2: Problem Definition

Gold prices are highly volatile, influenced by factors like inflation, interest rates, and currency
fluctuations. Traditional forecasting methods struggle to capture nonlinear relationships, leading
to inaccurate predictions. This project aims to develop a machine learning-based approach that
will improve predictive accuracy of these complex interactions by combining supervised
methods for price prediction and unsupervised methods for identifying market patterns. Unlike
single-model approaches, the hybrid method will leverage diverse features and cross-validation
to improve performance.



## Part 3: Methods

### Proposal

For preprocessing methods, we will use data cleaning, data transformation and feature
engineering. Data cleaning will improve data reliability by handling missing values, outliers, and
duplicates. Data transformation like scaling and logarithmic adjustments will standardize
metrics, enabling direct comparisons. Feature engineering will create moving averages, and
volatility indicators to find relationships between gold prices and economic factors.

For ML methods, we will use Random Forest, Linear Regression, and GMM. Random Forest is
useful for financial data due to its ability to capture nonlinear relationships, assess feature
importance, and reduce overfitting by averaging multiple decision trees. Linear Regression
provides a baseline by modeling the relationship between gold prices and macroeconomic
indicators like inflation and interest rates. Finally, GMM will help identify market patterns such
as high and low volatility periods, illustrating structural patterns that influence price movements.

### Midterm

#### Data Preprocessing Strategies

The first step was to obtain our data using Yahoo Finance and storing gold prices from the ticker (GC=F) as a pandas series where we have Gold Open, Gold Close, and Gold Volume. After getting the data, we indexed it by date and forward filled any missing values. Then, we decided to do feature engineering to create features that could explain price movement over time. This included adding a 5 day moving average, 100 day moving average for the Gold Close prices, and 5 day volatility. In addition, we take more data from FRED using its API. We take quarterly information like GDP, Interest Rates, CPI, and Unemployment. Since it is quarterly data, we use the same number for all dates in its specific quarter. Additionally, we take foreign exchange rates as more feeatures, including the exchange rate USD-CHF. After collecting all the economic indicators, we converted them into DataFrames, merged them into a single dataset, and reindexed everything to a daily frequency with forward filling to handle missing values. We also applied a log transformation to GDP to reduce skewness. Finally, we combined this economic data with the gold prices, calculated daily gold price changes, and saved the final dataset for modeling.

#### Supervised and Unsupervised Algorithms

As a major change from our initial proposal, we decided to change the algorithms we will implement since the initial attempts produced high MSE error on testing data versus training data. We chose to implement one unsupervised and one supervised learning model to classify our data into price predictions. 
For our unsupervised learning model, we are using KMeans, and for our supervised learning model, we are using Ridge Regression.

Supervised Learning Model (Ridge Regression): For our supervised learning method, we used Ridge Regression to forecast a specific daily Gold Close Price. We used ridge regression to add L2 regularization to prevent overfitting, especially with features that are very highly correlated, such as the USD/Franc and SP500. We split the data into 80% training and 20% testing to lead to the prediction of prices. We chose the ridge regression model because we wanted to prevent overfitting, so it can be more robust in predicting volatile markets. Additionally, the model handles multicollinearity well, making it suitable for financial datasets where predictor variables often move together, ensuring more stable and interpretable coefficient estimates.

Unsupervised Learning Model (KMeans):
K-means allows us to cluster similar data points that represent a common set of market trends. This can help us identify patterns in the gold market without using predefined labels. We implemented K-means with 4 clusters to group data into 4 types of market trends: bullish gold markets, bearish gold markets, stable markets, and high volatility periods each representing some commonalities between the features. K-Means makes sense to find these patterns in gold commodity behavior and cluster our data into these distinct categories. K-means alllows us to also deal with the high-dimentional data and organize it into these meaningful clusters. In the next section, we will talk more about what our clusters signify and justify what specific sets of feature values correspond to each of these clusters.


## Part 4: Results and Discussion

### Proposal

We will evaluate model performance using R², Mean Absolute Percentage Error (MAPE), and
k-fold cross-validation. R² measures the proportion of variance in gold prices captured by our
model, with higher values indicating better predictive accuracy. MAPE quantifies the average
prediction error in percentage terms, essential for assessing financial impacts. K-fold
cross-validation ensures robust performance by reducing overfitting and improving
generalization across data segments.

Our project aims to predict gold prices using market data, economic indicators, commodity
futures, and exchange rates. To improve prediction accuracy we will combine Random Forest
and Linear Regression for supervised learning with GMM for market pattern identification. We
prioritize sustainability and ethics by promoting accurate predictions to reduce speculative
mining and ensuring transparency in feature importance to mitigate data bias. Our expected
result is the predicted price of gold, derived from multiple features such as interest rates,
inflation, and exchange rates, alongside a high R² score, low MAPE, and consistent performance
validated through cross-validation, which will provide insights to future investors into future
market trends.

### Midterm

## Initial Results

After implementing the first models, we saw that there was high correlation between features such as the exchange rates and CPI in relation to GDP. This made us reduce the number of features so that one exchange rate and log GDP would become significant in our model. This also reduced our MSE in training data and testing data. We initially used a 80/20 split for training data and testing data but we wanted to make sure that time wasn't as impactful on the model. Thus, we implemented a K-Fold approach which tested our data into 5 testing sections and showed meaningful results.

## Ridge Regression w/K-fold Cross Validation Plots and Metrics

#### Model + Quantitative Metrics

![ridge_regression_model](https://github.gatech.edu/sdesai328/Group17MLProject/assets/70457/0da553d6-297e-4264-8f32-e47b51995ea6)

![ridge_regression_residuals](https://github.gatech.edu/sdesai328/Group17MLProject/assets/70457/792db509-94f4-4014-8722-02cb9bbc1d94)

Ridge Regression with K-Fold Cross-Validation:
- Average Training R²: 0.9998
- Average Test R²: 0.9983
- Average Training MSE: 51.6950
- Average Test MSE: 53.4709

#### Ridge Regression Model Discussion

## KMeans 

#### Determining Number of Groups

![kmeans_cluster_elbows](https://github.gatech.edu/sdesai328/Group17MLProject/assets/70457/aff7786f-1406-4ea8-b0a2-249e6f759800)

As shown by the plot above, once we reach 4 groups, there seems to be an elbow. The point suggests diminishing returns from adding more clusters, thus we chose to proceed with 4 clusters.

#### KMeans Model

![kmeans_image](https://github.gatech.edu/sdesai328/Group17MLProject/assets/70457/5ebce3cc-5025-40dc-9917-be61d8d7f3b1)

#### KMeans Model Discussion

## Part 5: References

- [1] R. Ghule and A. Gadhave, "Gold Price Prediction using Machine Learning,"
International Journal of Scientific Research in Engineering and Management, vol. 6, no.
7, pp. 1-5, 2022. [ResearchGate](https://www.researchgate.net/publication/362491642_Gold_Price_Prediction_using_Machine_Learning)

- [2] M. H. Alharbi, "Applying Machine Learning Techniques to Analyze and Explore
Precious Metals," Technology and Investment, vol. 15, no. 4, pp. 183-197, 2024. [SCIRP](https://www.scirp.org/journal/paperinformation?paperid=136582)

- [3] N. Zainal and Z. Mustaffa, "A Literature Review on Gold Price Predictive
Techniques," in Proceedings of the 2015 International Conference on Advanced
Mechatronic Systems, Beijing, China, 2015, pp. 252-257. [IEEE Xplore](https://ieeexplore.ieee.org/document/7324301)

- [4] G. K. Nair, N. Choudhary, and H. Purohit, "The Relationship between Gold Prices and Exchange Value of US Dollar in India," Emerging Markets Journal, vol. 5, no. 1, pp. 1–7, 2015. [Online](https://emaj.pitt.edu/ojs/emaj/article/view/66)

## Part 6: Contribution Table and Gantt Chart

[Google Sheets Gantt Chart](https://docs.google.com/spreadsheets/u/0/d/1NS2EDKeplf-mkVPEBQIdRBL6Zhtu8XMwBucQmdk5YFE/edit)

### Proposal

| Name     | Proposal Contributions |
|----------|------------------------|
| Aiden Wu | Contributed to the Literature Review, Background and Introduction, and Problem Definition. |
| Krish Gawande  | Contributed to the Github Pages, the Potential Results and Discussions, and Gantt Chart.          |
| Samay Desai  | Contributed to the Gantt Chart and the Potential Results and Discussions.           |
| Jason Li  | Contributed to the ML Methods to use and the Potential Dataset section.          |
| Liam Dolphin  | Contributed to the ML Methods to use and the Potential Dataset section.          |


---
### Midterm

| Name   | Midterm Contributions |
|--------|------------------------|
| Aidan  | Contributed to Model 1 Design & Selection, Model 1 Data Cleaning, Model 2 Design & Selection, Model 2 Data Cleaning, Model 1 and Model 2 Results Evaluation, and Midterm Report. |
| Liam   | Contributed to Model 1 Design & Selection, Model 1 Data Visualization, Model 2 Data Visualization, Model 1 and Model 2 Results Evaluation, and Midterm Report. |
| Jason  | Contributed to Model 1 Data Cleaning, Model 1 Feature Reduction, Model 2 Feature Reduction, Model 1 and Model 2 Results Evaluation, and Midterm Report. |
| Krish  | Contributed to Model 1 Feature Reduction, Model 2 Design & Selection, Model 2 Coding & Implementation, Model 1 and Model 2 Results Evaluation, and Midterm Report. |
| Samay  | Contributed to Model 1 Implementation & Coding, Model 2 Data Cleaning, Model 2 Feature Reduction, Model 1 and Model 2 Results Evaluation, and Midterm Report. |


