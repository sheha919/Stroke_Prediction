# Stroke_Prediction
- Author : Shehani Wetthasinghe
- Last modified: 11/18/2022

![image](https://user-images.githubusercontent.com/50593017/200030044-6d5a4985-db9a-430a-bb79-5007dc8ba86a.png)
Source : https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset

## Overview
According to the World Health Organization (WHO) stroke is the 2nd leading cause of death in the world. The goal of this study is to predict the chance of having a stroke based on following features;

1. gender: "Male", "Female" or "Other"
2. age: age of the patient
3. hypertension: 0 if the patient doesn't have hypertension, 1 if the patient has hypertension
4. heart_disease: 0 if the patient doesn't have any heart diseases, 1 if the patient has a heart disease
5. ever_married: "No" or "Yes"
6. work_type: "children", "Govt_jov", "Never_worked", "Private" or "Self-employed"
7. Residence_type: "Rural" or "Urban"
8. avg_glucose_level: average glucose level in blood
9. bmi: body mass index
10. smoking_status: "formerly smoked", "never smoked", "smokes" or "Unknown"*
*Note: "Unknown" in smoking_status means that the information is unavailable for this patient

Target variable : stroke: 1 if the patient had a stroke or 0 if not

Below histrogams illustrate the distribution of each feature with its mean and median values.
According to them, not any of features showing outliers.

![image](https://user-images.githubusercontent.com/50593017/202753632-0dc3c07c-5885-4b81-9cce-7ea54a3b40b3.png)
![image](https://user-images.githubusercontent.com/50593017/202753661-564c96be-7cea-4ac9-b351-664bf6e6c4ec.png)
![image](https://user-images.githubusercontent.com/50593017/202753679-e8fe6881-2064-402a-8d6d-f486f69c4d23.png)
![image](https://user-images.githubusercontent.com/50593017/202753697-ca229645-cbf2-40c3-a9ab-6edc3ea2c9ff.png)
![image](https://user-images.githubusercontent.com/50593017/202753720-3e2ad6ed-6ef1-4f51-a1ec-f8d5f0a392c0.png)
![image](https://user-images.githubusercontent.com/50593017/202753756-6120676d-6bd2-47cb-893c-a9ea1ccd839d.png)


The following heatmap shows how the features correlate each other.
  - The highest correlation shows between age and BMI which is 0.33
  - The lowest correlation shows between BMI and having a heart disease or not
![image](https://user-images.githubusercontent.com/50593017/202748908-dc8f9cf0-d35d-46ad-8457-2f30208627ab.png)

![image](https://user-images.githubusercontent.com/50593017/202754577-f36c6e50-a83b-4552-8745-7c5d4b4820d1.png)

- Most of the patients have average glucose level below ~ 140. But the patients with higher than 140 are increasing with as the age increment.
- Everyone with stroke fall above the age of 40 years.
- Most of patients are below the ~ 50 level of BMI.
- According to the CDC, patients can be catergorized as;
  - BMI is less than 18.5: Underweight range
  - BMI is 18.5 to 24.9: Healthy Weight range
  - BMI is 25.0 to 29.9: Overweight range
  - BMI is 30.0 or higher: Obese range
(source: https://www.cdc.gov/healthyweight/assessing/index.html)

- Most of the underweight patients fall under 20 years
- The majority of patients suffer from obesity are in between 20 and 60 years of age.
