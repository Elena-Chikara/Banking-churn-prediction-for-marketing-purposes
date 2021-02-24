<!DOCTYPE html>
<html>
 <head>
 </head>
<body>

<h2>Banking churn prediction for marketing purposes</h2>

:star: Star us on GitHub — it helps!

<p align="center"><img src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/main/Banking-churn-prediction-for-mar.gif" /></p>
<h3>Introduction </h3>

<small><p align="justify">It is always more difficult to retain rather than to obtain customers, as it places greater responsibility towards the business. Customer retention has become a crucial part of businesses as acquiring new customers is often more costly than keeping the current ones, which has led to the need to dedicate great amount of attention to churn prediction. Businesses have come to a point where they must take into significant consideration the clients’ personal characteristics and dynamic behavioral patterns of their financial transactions. Therefore, this project tends to use the clients’ demographic-based features and choice behavioral traits using individual transaction records regarding their credit cards. More generally, the proposed features can also be applied to churn prediction in other domains where demographic and behavioral data are available.</p>

<p align="justify">The time of Big Data is now! The availability of large-scale behavioral data has given the opportunity to businesses to conduct high-quality analysis of the clients’ behavior and make conclusions and predictions. It is crucial to understand that successful strategies lie on small and seemingly unimportant information. In addition, minimal information on when and where can have gigantic contribution to successful prediction and, consequently, to business success.<p>

<p align="justify">Churn prediction is a sphere of a great interest for the banking sector, as it is handling big data, as well. The purpose of this project is to build a model for churn prediction for an existing bank based on its own client database that includes demographic and transaction behavioral features. The dataset consists of the bank’s existing card owners and 19 features for each of them. Analyzing these features should lead us to creating a model that will successfully predict whether the card owner with his unique combination of demographic and financial characteristics is going to remain a bank’s client or he is going to leave.<p>

<p>Without further ado, we present the project “Banking churn prediction for marketing purposes”.<p>

<p>The project is done in the following phases:

- [Data Preprocessing](#data-preprocessing)
- [Features Analysis and Visualization](#features-analysis-and-visualization)
- [Model training](#model-training)
- [Conclusion](#conclusion)

</small></p>

## Data Preprocessing
<p>
<p align="justify">At the very beginning of the preprocessing phase, two important decisions were made: no data will be deleted (rows and columns) and outliers will remain outliers, as it is important to know which the rare cases are.</p>
 
<p align="justify">The dataset includes 10.127 entries with 19 features (excluding the feature 'CLIENTNUM', which is considered to be a clients' identification number, and the feature 'Attrition_Flag', which is the target variable) and it does not have any missing values. However, the feature 'Months_on_book' contained some untypical values that needed to be handled, more precisely, replaced using the KNNImputer method.</p>

<p align="justify">The dataset includes values that are “Unknown” and they will not be replaced with other values, as it is believed that they can represent a separate group of clients that can bring an important meaning to the analysis. The “Unknown” data cover 33.01% of the clients in the dataset and are contained in the features 'Education_Level', 'Marital_Status' and 'Income_Category'.</p>

<p align="justify">In the preprocessing phase different encoders were implemented in order to find out which one contributes to the higher accuracy achievement. For that reason, the used encoders were: One-hot-encoding, Category encoding, Count encoding and CatBoost encoding. Also, different types of Feature engineering methods were used, including: SMOTE, Log_transform and Feature generation. CatBoost encoding contributed for the best accuracy on test data and precision and recall and, as far as Feature engineering is concerned, Feature generation gave the best results.</p>

<p align="justify">In the end, the final combination of preprocessing techniques includes: StandardScaler for the numerical data, LabelEncoder and CatBoost encoding for the categorical data and Feature generation to create new features: 'gender_card', 'education_card', 'maritalStatus_card' and 'income_card'.</p>  
</p>

## Features Analysis and Visualization
 <p>
 <p>Utilizing Matplotlib, Seaborn and Pandas, we next analyzed the data.</p><br/>
 
 <p align="center"><img src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/target_class.png" /></p>
 <p>The dataset of the project is imbalanced, the target variable has more observations in the class of Existing Customer than the class of Attrited Customer.</p><br/>
 
 
 <p align="center">
<a><img width="58%" height="58%" src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/card_category.png"></a>
<img width="40%" height="40%" src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/card_category_bi.png"></a>
</p>
 
 <p align="justify">Most of the customers have blue card category, while all other card categories are less represented. This is of a great importance showing the dominant ownership of the Blue card against all of the other types of cards (Gold, Silver and Platinum). </p>
 <p align="justify">Clients with platinum cards are most likely to leave. Compared to the representation of each of the cards in the bank, the Platinum card is the least used card in the bank, and the most used card is Blue. Te reason for this trend can probably be connected with the height of clients' incomes, as it can be seen from one of the previous graphs that also clients with more that 120.000 usd incomes are more likely to leave the bank. In conclusion, the Platinum card is a type of card aimed for the highest social classes, which are probably trying to find ways to spend their high incomes. This makes this group wothed observing and stopping from trying another bank's card.<p><br/>
 
 
 <p align="center">
<a><img width="58%" height="58%" src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/income_category.png"></a>
<img width="40%" height="58%" src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/income_category_bi.png"></a>
</p>
 <p align="justify">Clients belonging on the two sides of income category are more likely to leave. Card owners with income less than 40.000$ are the majority of the dataset and, likewise, they could easily be the majority of churn clients.</p><br/>
 
   <p align="center"><img src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/Total_revolving_bal.PNG" /></p>
 <p align="justify">Most of the customers have Total Revolving Balance zero. This data signifies that most of the clients are returning the spent amount very inconsistently. The conclusion would be that either this clients have a necessity for higher revolving limit or that they have credit cards from other banks which have priority when returnig the spent amount.</p><br/> 
 
   <p align="center"><img src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/Avg_utilization_ratio.PNG" /></p>
 <p align="justify">This feature, according to the box-plot, shows that the more contacts the client brings to the bank within 12 months, the greater the probability to leave.</p><br/>
 
 <p align="center">
<a><img width="55%" height="58%" src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/Total_Revolving_Bal_bi.PNG"></a>
<img width="55%" height="58%" src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/Avg_Utilization_Ration_bi.PNG"></a>
</p>
<p align="justify"></p><br/>

<p align="center"><img src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/Contact_Count_12_mon.PNG" /></p>
 <p align="justify">This is a feature of a very big importance, because sometimes, the card owners who are not using their credit card bring more expenses to the bank, rather than income. Most of the clients have very low average utilisation ratio and as the ratio grows, the graph shows big slope downwards turning itself into skeweness to the right. This feaure perfectly explains the feature 'Total_Revolving_Bal', which means that either the clients are not returning the spent amounts or they are not spending their cards at all. 'Avg_utilization_ratio' finally shows that the majority of the clients have a huge lack of card expenditure, which is a serious drawback. The bank needs to work intensively on stimulating the clients to spend and revolve their card limits. Otherwise, it can become unimportant to them wheter they are clients of the bank or not, and finaly, they could attrite from the bank. The correlation matrix also shows that these two features have strong positive correlation of 0.6.</p><br/>

<p align="center">
<a><img width="45%" height="58%" src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/Total_Trans_Ct.PNG"></a>
<img width="45%" height="58%" src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/Total_Trans_Amt.PNG"></a>
<img width="50%" height="58%" src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/Total_Ct_Chng_Q4_Q1.PNG"></a>
</p>
 <p align="justify">The features 'Total_Trans_Ct' and 'Total_Trans_Amt' are highly positively correlated. Also, there can be a sigificant correlation with the feature Total_Ct_Chng_Q4_Q1. The greater these metrics are, the greater the probability for the clients to stay, and vice versa.</p><br/>


## Model training
<p align="justify">
During the process of model training 7 different algorithms were used:
</p>

<ul>
  <li>Naïve Bayes</li>
  <li>Support Vector Machine</li>
  <li>Decision Tree</li>
  <li>Random Forest</li>
  <li>K-Nearest Neighbor</li>
  <li>Gradient Boosting Tree</li>
  <li>XGBoost</li>
</ul>

<p align="justify">
All of the models were used with different techniques in the preprocessing phase and in the training phase.</p>

<p align="justify">In the training phase, the techniques that were used included Random search and Grid search of the best features. Although Random search and Grid search were tried, these techniques are excluded from the final model as they are resulting in slightly lower accuracy in precision and recall.</p>

<p align="justify">The following table describes all previously mentioned models with their accuracy achieved on the test dataset, sorted by descending:</p>
</p>

 <table style="width:100%">
  <tr>
    <th>Model</th>
    <th>Accuracy</th>
    <th>Model time</th>
  </tr>
  <tr>
    <td>XGBoost</td>
    <td>98.42</td>
    <td>00:00:00.510968</td>
  </tr>
  <tr>
    <td>Random Forest</td>
    <td>97.83</td>
    <td>00:00:00.963000</td>
  </tr>
  <tr>
    <td>Gradient Boosting Tree</td>
    <td>97.78</td>
    <td>00:00:07.220484</td>
  </tr>
 <tr>
    <td>Decision Tree</td>
    <td>96.00</td>
   <td>00:00:00.096043</td>
  </tr>
 <tr>
    <td>SVM</td>
    <td>91.02</td>
    <td>00:00:05.899189</td>
  </tr>
  <tr>
    <td>Naive Bayes</td>
    <td>90.47</td>
    <td>00:00:00.010004</td>
  </tr>
 <tr>
    <td>KNN</td>
    <td>87.22</td>
    <td>00:00:00.059553</td>
  </tr>
</table>

<p align="justify">The final model with the best prediction results in accuracy on test dataset, precision and recall was XGBoost with the following result:</p>
</p>

<p align="center">
<a><img width="30%" height="30%" src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/XGBoost-%20accuracy.PNG"></a>
<img src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/XGBoost-%20precision%20and%20recall.PNG"></a>
</p>

<p align="justify">
In addition, it is also necessary to construct the ROC curve for as a visual representation of the comparison of all of the trained models.
</p>

<p align="center"><img src="https://github.com/Elena-Chikara/Banking-churn-prediction-for-marketing-purposes/blob/Elena-Chikara-README-file/plots_and_tables/ROC%20curves%20of%20all%20models.PNG" /></p>

<p align="justify">
A ROC curve (receiver operating characteristic curve) is a graph showing the performance of a classification model at all classification thresholds on the basis of two parameters: True Positive Rate and False Positive Rate.</p>
 
<p align="justify">AUC (Area under the ROC Curve) measures the entire two-dimensional area underneath the entire ROC curve. ROC curve is actually quantified by AUC. The purpose is to see how much area has been covered by the ROC curve. If a perfect classifier is obtained, then the AUC score is 1.0. In the real world, an AUC score of 1.0 is not expected, but if the AUC score for the classifier is in the range of 0.6 to 0.9, then it is considered to be a good classifier.</p>

<p align="justify">As far as this project is concerned, the ROC graph shows that XGBoost has a small adventage in comparison with Random Forest and Gradient Boosting Tree. It achieves almost the perfect AUC score.</p>


## Conclusion
 <p>
<ul>
  <li>Having in mind the very unbalanced observed dataset that is used in the project, the produced result is exceptional.</li>
  <li>In the preprocessing phase several techniques were used in order to achieve the combination of KNNImputer, Standard Scaler, Label Encoding and CatBoostEncoding that provided for the best results.</li>
  <li>In the model testing phase seven models were used and compared in order to find the model that would give the highest percentage on the test dataset, precision and recall. XGBoost model is the model that makes the prediction most successfully.</li>
  <li>Churn prediction does not depend much on thr frature 'Gender', but it significantly depends on the feature 'Income_Category'. The higher the income, the greater the probability for the client to leave.</li>
  <li>According to the feature analysis using Feature Selection SelectKBest, the  five most important features are: 'Contacts_Count_12_mon', 'Total_Revolving_Bal', 'Total_Trans_Ct', 'Total_Ct_Chng_Q4_Q1', 'Avg_Utilization_Ratio'</li>
  <li></li>
  <li></li>
</ul> 
</p>


## References
<p>
https://seaborn.pydata.org/tutorial<br/>
https://core.ac.uk/download/pdf/83461632.pdf<br/>
https://machinelearningmastery.com/save-load-machine-learning-models-python-scikit-learn/
https://developers.google.com/machine-learning/crash-course/classification/roc-and-auc#:~:text=An%20ROC%20curve%20(receiver%20operating,False%20Positive%20Rate
https://medium.com/acing-ai/what-is-auc-446a71810df9
 </p>

</body>
