# Piracy Probabilities

---

### Table of Contents

1. [Problem Statement](#Problem-Statement)
2. [Background](#Background)
3. [Preprocessing & Modeling](#Preprocessing-and-Modeling)
4. [Conclusion and Recommendations](#Conclusion-and-Recommendations)
5. [Datasets](#Datasets)

---

### Problem Statement
Identify causal societal and developmental factors related to piracy. Using these factors we aim to create an effective model to prove that these factors are strong determinants of high piracy activity within the countries looking at attacks from 2010 onwards. 

---

### Background
When we think of maritime piracy it can often conjure up thoughts of wooden ships and eye patches, but it is still a problem that plagues us today. It is important to understand the societal and economic factors of piracy to redress causes of piracy and create a safer and more equitable world. The data was obtained from the National Geospatial-Intelligence Agency. We initially  obtained almost 8,000 observations of reported hostile acts against ships and mariners (pirate attacks) that ranged from 1978 to present. 

---

### Preprocessing and Modeling
We were initially able to pull over 7,000 observations of reported pirate attacks that ranged from 1978-present. Our project was more concerned with the effects of modern piracy, and as regions, economic factors and technologies would experience a great deal of change over the course of that time period we decided to look only at the attacks from 2010 to the present day.  This left us with approximately 3,5000 observations which was more than enough for our purposes.

By far, cleaning the data was the most time consuming portion of this project. The biggest issue we had was joining the different datas which required the featuring of the country column based on coordinate values. We were able to accomplish this using the Nominatim module from a python package called goepy. Nominatim’s usage policy restricted us to a maximum of 1 request per second which, given the initial size of the data, was very time consuming.  Attack observations were linked to our other data sets by associated countries or, if too far from the coastline, were labeled as International waters. Not all countries had records of the economic, educational, sea law and research and development for every single year so those values had to be imputed by what was available.

Classification models used were Logistic Regression, K-Nearest Neighbors, Random Forest. First, a baseline score was established then used GridSearchCV to identify the best scores and parameters generated from the models. 

|Model                               |R2 Traing Score   |R2 Testing Score  |Accuracy      |
|---                                 |---               |---               |---           |
|Logistic Regression                 |0.784             |0.717             |0.78 +- 0.10  |
|KNN                                 |0.997             |0.980             |0.96 +_ 0.04  |
|Random Forest                       |0.997             |0.980             |0.95 +- 0.09  |
|KNN w/o Location Features           |0.973             |0.849             |0.90 +_ 0.09  |
|Random Forest w/o Location Features |0.973             |0.879             |0.93 +- 0.10  |

---

### Conclusion and Recommendations
In conclusion most pirate attacks are happening in equatorial countries. Attacks tend to cluster in geographical choke points. Creating land based lookout and upping patrols points in these vulnerable areas. Most attacks are occurring in regions that have a higher poverty percentage, thus compounding problems in already troubled regions.There has been a steady decrease in pirating activity over the past decade. Cargo ships and tankers are at a higher risk. We recommend increased security on board for these types of vessels and adoption of sea laws should help curb piracy.

---

### Datasets
* [Anti-Shipping_Activity_Messages.csv](#'../datasets/Anti-Shipping_Activity_Messages.csv')
* [esri_w_country_columns.csv]('datasets/esri_w_country_columns.csv')
* [sea_law.csv]('datasets/sea_law.csv') 
* [eda_df.csv]('datasets/da_df.csv')
* [cleaned_pirate_activity_eda.csv]('datasets/cleaned_pirate_activity_eda.csv') 
* [math.csv]('datasets/math.csv') 
* [modeling.csv]('datasets/modeling.csv')
* [poverty,csv]('datasets/poverty.csv') 
* [rd_gdp.csv]('datasets/re_gdp.csv') 
* [reading.csv]('datasets/reading.csv')
* [research.csv]('datasets/research.csv')

---
