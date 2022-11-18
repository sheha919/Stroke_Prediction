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

![image](https://user-images.githubusercontent.com/50593017/202755071-3dcb0f7c-3738-434a-91ea-8cc803df457c.png)

- According to the above grid of bar charts;

  - Male and female patients have almost similar mean age, glucose levels and BMI
  - For adult patients, the BMI and glucose levels do not depend on the job type. (Never worked patients can be consider as teenagers, thus not catergorized as adults)
  - Seems like average glucose and BMI do not vary on the smoking status much.
  - Patients with hypertension and heart disease are also suffering from obesity and prediabetes or diabates.

- According to CDC;
  - Diabetes: above 126 mg/dL
  - Prediabetes: 100 – 125 mg/dL
  - Normal: Below 99 mg/dL
 
(source: https://www.cdc.gov/diabetes/basics/getting-tested.html#:~:text=Fasting%20Blood%20Sugar%20Test&text=A%20fasting%20blood%20sugar%20level,higher%20indicates%20you%20have%20diabetes.)

**Model Performences**
- Performence of optimized logistic regression model
![image](https://user-images.githubusercontent.com/50593017/202756102-13ec4ad0-bde4-4c25-9e8a-d0a3c0d788a2.png)

- Performence of optimized KNN model
![image](https://user-images.githubusercontent.com/50593017/202756215-b4f824fa-a7e7-4bd5-b41e-c4df294846d9.png)

- Performence of optimized random forest model
![image](https://user-images.githubusercontent.com/50593017/202756350-2e748852-eac7-4af5-bc53-367af7539f06.png)

- The Summary

|Model|Precision|Recall|F1 Score|Accuracy|
|---|---|---|---|---|
|Logistic Regression|0\.131|0\.806|0\.225|0\.73|
|KNN|0\.075|0\.242|0\.115|0\.818|

- Even though, the highest accuracy is co,img from the optimized random forest model, here we are trying to maximize recall score to minimize the rist on patietns.
|Random Forest|0\.129|0\.145|0\.136|0\.911|
