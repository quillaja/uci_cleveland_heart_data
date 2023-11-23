# UCI Heart Disease Dataset

Just the Cleveland dataset with 303 instances. The original numeric encodings of categorical data are retained, including in the field `target`. I replaced 6 no-data values indicated by `?` with `NULL` so pandas will recognize them as `NA`. Additional descriptive metadata is in the table below.

Data source:
https://archive.ics.uci.edu/dataset/45/heart+disease

Accessed: 2023-11-22

From file: `processed.cleveland.data`

## Fields

role| field | description | type | values | comment 
---|---|---|---|---|---|
feature| age | age in years| integer ||
feature| sex | patient's sex| categorical |  0 = female, 1 = male | 
feature| cp | chest pain type experienced| categorical | 1 = typical [angina](https://www.mayoclinic.org/diseases-conditions/angina/symptoms-causes/syc-20369373), 2 = atypical angina, 3 = non-anginal pain, 4 = asymptomatic |
feature| trestbps | resting blood pressure (mmHg on admission to hospital)| integer ||
feature| chol | serum cholesterol in mg/dl| integer ||
feature| fbs | fasting blood sugar > 120 mg/dl| categorical | 0 = false, 1 = true  |
feature| restecg | resting electrocardiographic results| categorical | 0 = normal, 1 = abnormality, 2 = hypertrophy | abnormality = having [ST-T wave](https://litfl.com/st-segment-ecg-library/) abnormality; hypertrophy = showing probable or definite [left ventricular hypertrophy](https://litfl.com/left-ventricular-hypertrophy-lvh-ecg-library/) by Estes' criteria
feature| thalach | maximum heart rate achieved| integer ||
feature| exang | exercise induced angina| categorical | 0 = no, 1 = yes  | 
feature| oldpeak | ST depression induced by exercise relative to rest| float ||
feature| slope | the slope of the peak exercise ST segment| categorical | 1 = upsloping, 2 = flat, 3 = downsloping | 
feature| ca | number of major vessels (0-3) colored by [fluoroscopy](https://www.hopkinsmedicine.org/health/treatment-tests-and-therapies/fluoroscopy-procedure)| integer; contains 4 NULL values | |
feature| thal | result of [myocardial perfusion scan](https://www.hopkinsmedicine.org/health/treatment-tests-and-therapies/myocardial-perfusion-scan-stress) | categorical | 3 = normal, 6 = fixed defect, 7 = reversable defect; contains 2 NULL values | This test locates heart muscle that does not absorb tracer dye and is therefore not getting blood flow. A reversible defect is not visible at rest but appears during exercise-induced stress. A fixed defect is visible both at rest and during exercise. _Note_: This field is often described as [thalassemia](https://en.wikipedia.org/wiki/Thalassemia), but I don't think that is correct.
target/label| target | diagnosis of heart disease (angiographic disease status)| categorical | 0 = healthy/absence of heart disease, (1, 2, 3, 4) = sick/presence of heart disease | sometimes this field is called `num`

Additional sources consulted:
1. https://www.kaggle.com/code/tentotheminus9/what-causes-heart-disease-explaining-the-model
2. https://towardsdatascience.com/heart-disease-uci-diagnosis-prediction-b1943ee835a7