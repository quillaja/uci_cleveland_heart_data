# UCI Heart Disease Dataset

Just the Cleveland dataset with 303 instances. This file is based on `cleve.mod` which apparently is a modification by Gennari in 1990 of the original dataset that replaced numerically encoded categorical data with descriptive text encodings. I have expanded those text encodings to be longer and more descriptive. I replaced 6 no-data values indicated by `?` with `NULL` so pandas will recognize them as `NA`. Additional descriptive metadata is in the table below.

Data source:
https://archive.ics.uci.edu/dataset/45/heart+disease

Accessed: 2023-11-22

From file: `cleve.mod`

## Original note:

This note is at the top of `cleve.mod`.
```
% John Gennari
% 3/13/90
%
% This is Dr. Detrano's database modified to be a real MIXED dataset.
%
% Attributes: 8 symbolic, 6 numeric.
%  Age; sex; chest pain type (angina, abnang, notang, asympt)
%  Trestbps (resting blood pres); cholesteral; fasting blood sugar < 120
%  (true or false); resting ecg (norm, abn, hyper); max heart rate; 
%  exercise induced angina (true or false); oldpeak; slope (up, flat, down)
%  number of vessels colored (???); thal (norm, fixed, rever). Finally, the
%  class is either healthy (buff) or with heart-disease (sick).
%
% Original atts: 
%   age; sex (1,0); cp (1-4); trestbps; chol; fbs (1,0); restecg (0,1,2); 
%   thalach; exang (1,0); oldpeak; slope (1,2,3); ca; thal (3,6,7);
%   class att: 0 is healthy, 1,2,3,4 is sick.
```

## Fields

role| field | description | type | values | comment 
---|---|---|---|---|---|
feature| age | age in years| integer ||
feature| sex | patient's sex| categorical | male, female | 
feature| cp | chest pain type experienced| categorical | [angina](https://www.mayoclinic.org/diseases-conditions/angina/symptoms-causes/syc-20369373), atypical_angina, nonanginal, asymptomatic |
feature| trestbps | resting blood pressure (mmHg on admission to hospital)| integer ||
feature| chol | serum cholesterol in mg/dl| integer ||
feature| fbs | fasting blood sugar > 120 mg/dl| categorical | true, false |
feature| restecg | resting electrocardiographic results| categorical | normal, hypertrophy, abnormality | abnormality = having [ST-T wave](https://litfl.com/st-segment-ecg-library/) abnormality; hypertrophy = showing probable or definite [left ventricular hypertrophy](https://litfl.com/left-ventricular-hypertrophy-lvh-ecg-library/) by Estes' criteria
feature| thalach | maximum heart rate achieved| integer ||
feature| exang | exercise induced angina| categorical | true, false | 
feature| oldpeak | ST depression induced by exercise relative to rest| float ||
feature| slope | the slope of the peak exercise ST segment| categorical | flat, up, down | 
feature| ca | number of major vessels (0-3) colored by [fluoroscopy](https://www.hopkinsmedicine.org/health/treatment-tests-and-therapies/fluoroscopy-procedure)| integer; contains 4 NULL values | |
feature| thal | result of [myocardial perfusion scan](https://www.hopkinsmedicine.org/health/treatment-tests-and-therapies/myocardial-perfusion-scan-stress) | categorical | normal, fixed, reversible; contains 2 NULL values | This test locates heart muscle that does not absorb tracer dye and is therefore not getting blood flow. A reversible defect is not visible at rest but appears during exercise-induced stress. A fixed defect is visible both at rest and during exercise. Note: This field is often described as [thalassemia](https://en.wikipedia.org/wiki/Thalassemia), but I don't think that is correct.
target/label| target | diagnosis of heart disease (angiographic disease status)| categorical | healthy, sick | sometimes this field is called `num`

Additional sources consulted:
1. https://www.kaggle.com/code/tentotheminus9/what-causes-heart-disease-explaining-the-model
2. https://towardsdatascience.com/heart-disease-uci-diagnosis-prediction-b1943ee835a7