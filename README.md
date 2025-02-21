# Group17MLProject

Hi everyone! This is the link to our Machine Learning Project Github Pages.
https://github.gatech.edu/pages/sdesai328/Group17MLProject/



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
- b. Economic indicators like inflation, interest rates, and GDP growth: [FRED](https://fred.stlouisfed.org/)
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

## Part 4: Results and Discussion

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

## Part 5: References

- [1] R. Ghule and A. Gadhave, "Gold Price Prediction using Machine Learning,"
International Journal of Scientific Research in Engineering and Management, vol. 6, no.
7, pp. 1-5, 2022. [ResearchGate](https://www.researchgate.net/publication/362491642_Gold_Price_Prediction_using_Machine_Learning)

- [2] M. H. Alharbi, "Applying Machine Learning Techniques to Analyze and Explore
Precious Metals," Technology and Investment, vol. 15, no. 4, pp. 183-197, 2024. [SCIRP](https://www.scirp.org/journal/paperinformation?paperid=136582)

- [3] N. Zainal and Z. Mustaffa, "A Literature Review on Gold Price Predictive
Techniques," in Proceedings of the 2015 International Conference on Advanced
Mechatronic Systems, Beijing, China, 2015, pp. 252-257. [IEEE Xplore](https://ieeexplore.ieee.org/document/7324301)

## Part 6: Contribution Table and Gantt Chart

[Google Sheets Gantt Chart](https://docs.google.com/spreadsheets/u/0/d/1NS2EDKeplf-mkVPEBQIdRBL6Zhtu8XMwBucQmdk5YFE/edit)


| Name     | Proposal Contributions |
|----------|------------------------|
| Aiden Wu | Contributions          |
| Krish Gawande  | Contributions          |
| Samay Desai  | Contributions          |
| Jason Li  | Contributions          |
| Liam Dolphin  | Contributions          |
