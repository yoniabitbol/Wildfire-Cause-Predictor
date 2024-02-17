# SOEN471 Group Project
| Team Member  | Student ID |
| ------------- | ------------- |
| Adir Ben-David  | 40190551  |
| Reuven Ostrofsky  | 40188881  |
| Jonathan Abitbol  | 40190550  |
| Jiayi Chen  | 40110997 |

### Project summary report link:
[Project Summary](https://docs.google.com/document/d/1sDv3xksV7pnLMhQkiMD0oe-1JXeBmPkOfG9xYf7Pmsw/edit?usp=sharing)

## Abstract
Our goal is to predict and classify the most possible cause of a wildfire given the detailed location, time, and other characteristics of the wildfire. We decide to apply the supervised machine learning method to solve this problem. The dataset we used can be found on Kaggle. It contains a spatial database of wildfires that occurred in the United States from 1992 to 2015. This data is originally generated to support the national Fire Program Analysis (FPA) system. In addition to the prediction task, we will compare the performance of different tree-based models in this classification task. The three models chosen are the Decision Tree, Random Forests, and Gradient Boosting Tree. The result will be evaluated and visualized by comparing accuracy, F1 score, confusion matrix, etc.

## Introduction
Wildfires are significant environmental hazards that pose threats to ecosystems, human lives, and property. Understanding the causes of wildfires is crucial for effective fire management, prevention, and mitigation strategies. Our project aims to accelerate the analysis of wildfire causes and, if applicable, predict future wildfire causes to facilitate proactive measures.

To fully use our dataset, We will begin by preprocessing the dataset, which includes analyzing features, removing noise, and extracting relevant information. Specific preprocessing techniques such as outlier removal, normalization, and handling missing values will be performed to improve the quality of the data. With the cleaned dataset, we will use different tree classifier algorithms to learn the patterns and predict the cause of the wildfire. Depending on the results, we will fine-tune the models to optimize performance and generalize well to unseen data. 

A crucial aspect of our project is the comparison of different tree-based algorithms including decision trees, random forests, and gradient boosting tree to determine which one is most suitable for wildfire cause prediction. An accuracy of around 70% is expected. We will consider factors such as model accuracy, F1 score, and computational efficiency to make informed decisions about algorithm selection.

## Research Questions
* Is it possible to predict or decide the cause of the wildfires based on the wildfire information like time, location, size, etc?
* Among three different tree-based classification algorithms, which one will have the best performance for the wildfire causes prediction problem?

## Datasets
The dataset can be found [here](https://www.kaggle.com/datasets/rtatman/188-million-us-wildfires/data).

The original dataset is stored in a sqlite3 database file. Inside the database, the fires table which has 39 columns and 1880465 rows will be extracted as a CSV file for this task. Among those 39 columns, the features we think will be helpful for prediction task are:
* SOURCE_SYSTEM_TYPE (string):  Type of source database or system that the record was drawn from (federal, nonfederal, or interagency).
* SOURCE_SYSTEM (string): Name of or other identifier for source database or system that the record was drawn from. 
* FIRE_YEAR (int64): Calendar year in which the fire was discovered or confirmed to exist.
* DISCOVERY_DATE (float64): Date on which the fire was discovered or confirmed to exist.
* DISCOVERY_DOY (int64): Day of year on which the fire was discovered or confirmed to exist.
* DISCOVERY_TIME (int64): Time of day that the fire was discovered or confirmed to exist.
* STAT_CAUSE_DESCR (string): Description of the (statistical) cause of the fire.
* CONT_DATE (float64): Date on which the fire was declared contained or otherwise controlled (mm/dd/yyyy where mm=month, dd=day, and yyyy=year).
* CONT_DOY (float64): Day of year on which the fire was declared contained or otherwise controlled.
* CONT_TIME (int64): Time of day that the fire was declared contained or otherwise controlled (hhmm where hh=hour, mm=minutes).
* FIRE_SIZE (float64): Estimate of acres within the final perimeter of the fire.
* FIRE_SIZE_CLASS (string): Code for fire size based on the number of acres within the final fire perimeter expenditures (A=greater than 0 but less than or equal to 0.25 acres, B=0.26-9.9 acres, C=10.0-99.9 acres, D=100-299 acres, E=300 to 999 acres, F=1000 to 4999 acres, and G=5000+ acres).
* LATITUDE (float64): Latitude (NAD83) for point location of the fire (decimal degrees).
* LONGITUDE (float64): Longitude (NAD83) for point location of the fire (decimal degrees).
* OWNER_CODE (float64): Code for primary owner or entity responsible for managing the land at the point of origin of the fire at the time of the incident.
* OWNER_DESCR (string): Name of primary owner or entity responsible for managing the land at the point of origin of the fire at the time of the incident.
* STATE (string): Two-letter alphabetic code for the state in which the fire burned (or originated), based on the nominal designation in the fire report.
* COUNTY (string): County, or equivalent, in which the fire burned (or originated), based on nominal designation in the fire report.
* FIPS_CODE (int64): Three-digit code from the Federal Information Process Standards (FIPS) publication 6-4 for representation of counties and equivalent entities.
* FIPS_NAME (string): County name from the FIPS publication 6-4 for representation of counties and equivalent entities.

Those features will be transformed, combined, encoded, and cleaned to remove redundancies and improve efficiency in the data preprocessing progress.

## Algorithms
Three tree-based algorithms will be applied and compared, they are:
1. Decision Tree (sklearn):
    * A machine learning algorithm based on a tree structure used for classification and regression tasks.
    * At each decision node, the algorithm selects a feature and splits the dataset into different branches based on the value of that feature until reaching the final leaf nodes.
    * It is easy to understand and interpret with high performance in handling categorical data, and minimal data preprocessing requirements.
2. Random Forests (sklearn):
    * Random Forests is an ensemble learning method that combines multiple decision trees to perform classification and regression tasks.
    * Each decision tree is trained independently on different subsets of the data and votes for the final prediction.
    * Random Forests help reduce the overfitting problem caused by the imbalanced dataset.
3. Gradient Boosting Tree (xgboost):
    * Gradient Boosting Tree is also an ensemble learning method that sequentially trains multiple decision trees.
    * Unlike Random Forests, Gradient Boosting Tree gradually improves the model by iteratively fitting the residuals to minimize the loss function.
    * Gradient Boosting Tree has a strong ability to fit complex relationships, handle various types of data, and capture nonlinear relationships between features.
  




