## Introduction

Sepsis is a major public health concern with significant morbidity, mortality, and healthcare expenses. Early detection and antibiotic treatment of sepsis improve outcomes. However, although professional critical care societies have proposed new clinical criteria that aid sepsis recognition, the fundamental need for early detection and treatment remains unmet. In response, researchers have proposed algorithms for early sepsis detection, but directly comparing such methods has not been possible because of different patient cohorts, clinical variables and sepsis criteria, prediction tasks, evaluation metrics, and other differences. To address these issues, the PhysioNet/Computing in Cardiology Challenge 2019 facilitated the development of automated, open-source algorithms for the early detection of sepsis from clinical data.

To do this the Knowledge Discovery in Databases (KDD) process will be adopted. This process consists of 4 steps:

Selecting and extracting the multivariate time series data set from the database.
Pre-processed and cleaned up the time series into a tidy dataset by exploring the data, handling missing data, and removing noise / outliers.
Building a predictive model allowing to associate the time series of biomedical measurements with a real-time severity indicator (probability of mortality) by implementing several machine learning algorithms.
Evaluation and validation. The use of two databases provides an opportunity to validate the different predictive models that will be produced.

## Data

Click '[here](https://archive.physionet.org/users/shared/challenge-2019/)' to download the complete training database (42 MB), consisting of two parts: training set A (20,336 subjects) and B (20,000 subjects). Each training data file provides a table with measurements over time. Each column of the table provides a sequence of measurements over time (e.g., heart rate over several hours), where the header of the column describes the measurement. Each row of the table provides a collection of measurements at the same time (e.g., heart rate and oxygen level at the same time). The table is formatted in the following way:

HR |O2Sat|Temp|...|HospAdmTime|ICULOS|SepsisLabel
---|---|---|---|---|---|---|
NaN|  NaN| NaN|...|        -50|     1|          0
 86|   98| NaN|...|        -50|     2|          0
 75|  NaN| NaN|...|        -50|     3|          1
 99|  100|35.5|...|        -50|     4|          1
 
 There are 40 time-dependent variables HR, O2Sat, Temp ..., HospAdmTime, which are described here. The final column, SepsisLabel, indicates the onset of sepsis according to the Sepsis-3 definition, where 1 indicates sepsis and 0 indicates no sepsis. Entries of NaN (not a number) indicate that there was no recorded measurement of a variable at the time interval.
 
 ## Approach
 
 1) Combined all the .psv files into a single file
 2) Handling missing values through- forward and backward filling
 3) SMOTE analysis was used for handling labelled data imbalance
 4) Feature Engineering
 5) Model building and prediction
 
 ## Results 
 We used 3 classifier models to test the outcome of the prediction namely: Random Forest, Logictic Regression and XGBoost classifiers. Based on the evaluation metrics result after prediction,  XGBoost have the best results with an accuracy of ~ 95%.
 ![image](https://user-images.githubusercontent.com/39477180/222509844-6bef1d17-9277-4cb5-abee-f663d53a0b71.png)

 
 ## Conclusion
 The project has a scope of continuing with further research on the importance of the features, better model building and under the guidance of a good health science domain expert.

