# NYC Boiler Defect Prediction

This was our semester-long project for Machine Learning for Cities course by Daniel Neill at NYU CUSP. Team members: [Cyrus Blankinship](https://github.com/cyrusblankinship), [Sam Burns](https://github.com/seeess1), [Max Brueckner-Humphreys](https://github.com/mbh329), and [Pablo Mandiola](https://github.com/pmandiola)

## Problem: Identifying and predicting boiler defects in NYC through exploratory analysis and machine learning modeling

The goal of the project is an exploratory analysis of boiler defect detection within New York City with the aim of predicting defects by  geographies and building types, to aide the DOB in their inspection process. With a targeted geography in mind, DOB inspectors can better pinpoint where issues might arise and allocate resources to these areas. By including ACS data, we also aimed to identify certain demographic features that might be more prone to building neglect.

## Data sources:

Our analysis is based on [boiler inspection and certification data](https://data.cityofnewyork.us/Housing-Development/DOB-NOW-Safety-Boiler/52dp-yji6) published by the NYC Department of Environmental Protection (DEP) and the Department of Buildings (DOB), building profile information from [PLUTO](https://www1.nyc.gov/site/planning/data-maps/open-data/dwn-pluto-mappluto.page) provided by the NYC Department of City Planning (DCP), and demographic data published by the U.S. Census Bureau’s [American Community Survey (ACS)](https://www.census.gov/programs-surveys/acs/data.html).

DOB NOW data available on NYC Open Data for boiler inspections only extends as far back as 2017. To gather historical data from the DOB’s Building Information Search portal, we constructed a [data scraping script](https://github.com/cyrusblankinship/NYC_Boiler_Defect_Prediction/blob/master/Scraping%20boiler%20data.ipynb) that gathered pertinent information for boilers going all the way back to 1993.

## Data Exploration and Analysis:

Initial data exploration showed that our dataset was highly imbalanced, with only 12% of DOB boiler inspections detecting a defect. We used several balancing techniques - under-sampling, over-sampling, and Synthetic Minority Over-sampling (SMOTE) - to rebalance our data and get better performance in our models.

For modeling and prediction we used 3 classic machine learning techniques: [Naive Bayes](https://github.com/cyrusblankinship/NYC_Boiler_Defect_Prediction/blob/master/Analysis_Naive_Bayes.ipynb), [Random Forest](https://github.com/cyrusblankinship/NYC_Boiler_Defect_Prediction/blob/master/random_forest.ipynb), and [Bayesian Networks](https://github.com/cyrusblankinship/NYC_Boiler_Defect_Prediction/blob/master/Analysis_Bayesian%20Network.ipynb). Although the results of the predictions were underwhelming, there are useful statistics that each model provided. We identified recall in our data as an important metric for evaluation of the models performance due to the high class imbalance: the two models that gave us the best results were Gaussian Naive Bayes utilizing the SMOTE sampling technique and our Random Forest Classifier with undersampled data and 100 trees. 
