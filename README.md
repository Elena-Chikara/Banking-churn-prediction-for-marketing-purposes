<!DOCTYPE html>
<html>
 <head>
 </head>
<body>

<h2>Banking churn prediction for marketing purposes</h2>

:star: Star us on GitHub — it helps!


<h3>Introduction </h3>

<small><p>
 
It is always more difficult to retain rather than to obtain customers, as it places greater responsibility towards the business. Customer retention has become a crucial part of businesses as acquiring new customers is often more costly than keeping the current ones, which has led to the need to dedicate great amount of attention to churn prediction. Businesses have come to a point where they must take into significant consideration clients’ personal characteristics and dynamic behavioral patterns of their financial transactions. Therefore, this project tends to use the clients’ demographic-based features and choice behavioral traits using individual transaction records regarding their credit cards. More generally, the proposed features can also be applied to churn prediction in other domains where demographic and behavioral data are available.</p>

<p>The time of Big Data is now! The availability of large-scale behavioral data has given the opportunity to businesses to conduct high-quality analysis of the clients’ behavior and make conclusions and predictions. It is crucial to understand that successful strategies lie on small and seemingly unimportant information. In addition, minimal information on when and where can have gigantic contribution to successful prediction and, consequently, to business success.<p>

<p>Churn prediction is a sphere of a great interest for the banking sector, as it is handling big data, as well. The purpose of this project is to build a model for churn prediction for an existing bank based on its own client database that includes demographic and transaction behavioral features. The dataset consists of the bank’s existing card owners and 19 features for each of them. Analyzing these features should lead us to creating a model that will successfully predict whether the card owner with his unique combination of demographic and financial characteristics is going to remain a bank’s client or he is going to leave.<p>

<p>Without further ado, we present the project “Banking churn prediction for marketing purposes”.<p>

<p>The project is done in the following phases:

- [Data Preprocessing](#data-preprocessing)
- [Features Analysis and Visualization](#features-analysis-and-visualization)
- [Models implementation](#models-implementation)
- [Conclusion](#conclusion)

</small></p>

## Data Preprocessing
<p>
At the very beginning of the preprocessing phase, two important decisions were made: no data will be deleted (rows and columns) and outliers will remain outliers, as it is important to know which the rare cases are.
 
The dataset includes 10.126 examples with 19 features and it does not have any missing values. However, the feature 'Months_on_book' contained some untypical values that needed to be handled, more precisely, replaced using the KNNImputer method.
The dataset includes values that are “Unknown” and they will not be replaced with other values, as it is believed that they can represent a separate group of clients that can bring an important meaning to the analysis. The “Unknown” data cover 33.01% of the clients in the dataset and are contained in the features 'Education_Level', 'Marital_Status' and 'Income_Category'.

The techniques used in the preprocessing phase include StandardScaler for the numerical data, LabelEncoder and CatBoost encoding for the categorical data, and Feature generation to create new features: 'gender_card', 'education_card', 'maritalStatus_card' and 'income_card'.  
</p>

## Features Analysis and Visualization
 <p>
 <p>Utilizing Matplotlib, Seaborn and Pandas, we next analyzed the data.</p><br/>
 
 <p align="center"><img src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/target_class.png" /></p>
 <p>The dataset of the project is imbalanced, the target variable has more observations in the class of Existing Customer than the class of Attrited Customer.</p><br/>
 
 <p align="center"><img src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/Card%20category.PNG" /><p align="center"><img src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/card_category_bi.png" /></p>
 <p>Most of the customers have blue card category, while all other card categories are less represented. This is of a great importance showing the dominant ownership of the Blue card against all of the other types of cards (Gold, Silver and Platinum). </p>
 <p>Clients with platinum cards are most likely to leave. Compared to the representation of each of the cards in the bank, the Platinum card is the least used card in the bank, and the most used card is Blue. Te reason for this trend can probably be connected with the height of clients' incomes, as it can be seen from one of the previous graphs that also clients with more that 120.000 usd incomes are more likely to leave the bank. In conclusion, the Platinum card is a type of card aimed for the highest social classes, which are probably trying to find ways to spend their high incomes. This makes this group wothed observing and stopping from trying another bank's card.<p><br/>
  
   <p align="center"><img src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/income_category.png" />
   <p align="center"><img src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/Income_category_bi.PNG" />
</p>
 <p>Clients belonging on the two sides of income category are more likely to leave. Card owners with income less than 40.000$ are the majority of the dataset and, likewise, they could easily be the majority of churn clients.</p><br/>
 
   <p align="center"><img src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/credit_limit.png" /></p>
 <p> Enter text here </p><br/> 
 
   <p align="center"><img src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/all_features.png" /></p>
 <p> Enter text here </p><br/> 

## Models Implementation
 <p>
 Enter text 
</p>

## Conclusion
 <p>
 Enter text 
</p>


## References
<p>
https://seaborn.pydata.org/tutorial<br/>
https://core.ac.uk/download/pdf/83461632.pdf<br/>
https://machinelearningmastery.com/save-load-machine-learning-models-python-scikit-learn/ 
 </p>

</body>
