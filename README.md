# Piracy Probabilities

---

### Table of Contents

1. [Problem Statement](#Problem-Statement)
2. [Preprocessing & Modeling](#Preprocessing-and-Modeling)
3. [Conclusion and Recommendations](#Conclusion-and-Recommendations)
4. [Datasets](#Datasets)

---

### Problem Statement
Identify and rank causal societal and developmental factors related to piracy. Using these factors we aim to create an effective model to prove that these factors are strong determinants of high piracy activity within the countries in our scope. 

What types of pirate attacks exist?

Our data defined pirate attacks as assaults, suspicious approaches, kidnapping, attempted boarding and hijacking that occur out at sea.

---

### Preprocessing and Modeling
We were initially able to pull over 7,000 observations of reported pirate attacks that ranged from 1978-present. Our project was more concerned with the effects of modern piracy, and as regions, economic factors and technologies would experience a great deal of change over the course of that time period we decided to look only at the attacks from 2010 to the present day.  This left us with approximately 3,5000 observations which was more than enough for our purposes.
By far, cleaning the data was the most time consuming portion of this project. The biggest issue we had was joining the different datas which required the featuring of the country column based on coordinate values. We were able to accomplish this using the Nominatim module from a python package called goepy. Nominatim’s usage policy restricted us to a maximum of 1 request per second which, given the initial size of the data, was very time consuming.  Attack observations were linked to our other data sets by associated countries or, if too far from the coastline, were labeled as International waters. Not all countries had records of the economic, educational, sea law and research and development for every single year so those values had to be imputed by what was available.


---

### Conclusion and Recommendations



---

### Datasets
* [eda_df.csv]('datasets/da_df.csv'): 
* [math.csv]('datasets/math.csv'): 
* [modeling.csv]('datasets/modeling.csv'):
* [poverty,csv]('datasets/poverty.csv'):
* [rd_gdp.csv]('datasets/re_gdp.csv'):
* [reading.csv]('datasets/reading.csv'):
* [research.csv]('datasets/research.csv'):

---
