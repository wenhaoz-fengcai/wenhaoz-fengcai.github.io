---
title: "The Derivation of an ICD-10-based Trauma-related Mortality Model Utilizing Machine Learning."
collection: publications
permalink: /publication/icd10
date: 2021-09-20
venue: 'The Journal of Trauma and Acute Care Surgery'
paperurl: 'https://europepmc.org/article/med/34554135'
---
**Background**

Existing mortality prediction models have attempted to quantify injury burden following trauma-related admissions with the most notable being the Injury Severity Score (ISS). Although easy to calculate, it requires additional administrative coding. International Classification of Diseases (ICD)-based models such as the Trauma Mortality Prediction Model (TMPM-ICD10) circumvent these limitations, but they use linear modeling, which may not adequately capture the intricate relationships of injuries on mortality. Using ICD-10 coding and machine learning (ML) algorithms, the present study used the National Trauma Data Bank to develop mortality prediction models whose performance was compared with logistic regression, ISS, and TMPM-ICD10.

**Methods**

The 2015 to 2017 National Trauma Data Bank was used to identify adults following trauma-related admissions. Of 8,021 ICD-10 codes, injuries were categorized into 1,495 unique variables. The primary outcome was in-hospital mortality. eXtreme Gradient Boosting (XGBoost), a ML technique that uses iterations of decision trees, was used to develop mortality models. Model discrimination was compared with logistic regression, ISS, and TMPM-ICD10 using receiver operating characteristic curve and probabilistic accuracy with calibration curves.

**Results**

Of 1,611,063 patients, 54,870 (3.41%) experienced in-hospital mortality. Compared with those who survived, those who died more frequently suffered from penetrating trauma and had a greater number of injuries. The XGBoost model exhibited superior receiver operating characteristic curve (0.863 [95% confidence interval (CI), 0.862-0.864]) compared with logistic regression (0.845 [95% CI, 0.844-0.846]), ISS (0.828 [95% CI, 0.827-0.829]), and TMPM-ICD10 (0.861 [95% CI, 0.860-0.862]) (all p < 0.001). Importantly, the ML model also had significantly improved calibration compared with other methodologies (XGBoost, coefficient of determination (R2) = 0.993; logistic regression, R2 = 0.981; ISS, R2 = 0.649; TMPM-ICD10, R2 = 0.830).

**Conclusion**

Machine learning models using XGBoost demonstrated superior performance and calibration compared with logistic regression, ISS, and TMPM-ICD10. Such approaches in quantifying injury severity may improve its utility in mortality prognostication, quality improvement, and trauma research.