# Stroke_Prediction
- Author : Shehani Wetthasinghe
- Last modified: 12/05/2022

![image](https://user-images.githubusercontent.com/50593017/200030044-6d5a4985-db9a-430a-bb79-5007dc8ba86a.png)
Source : https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset

## Overview
According to CDC;

“A stroke, sometimes called a brain attack, occurs when something blocks blood supply to part of the brain or when a blood vessel in the brain bursts. In either case, parts of the brain become damaged or die. A stroke can cause lasting brain damage, long-term disability, or even death.”

## The goal of the project

To predict the chance of having a stroke based on common risk factors using machine learning techniques.



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


# The Summary

**Performence of pre-optimized Models**

![image](https://user-images.githubusercontent.com/50593017/205737738-6e034c27-c22b-4d32-8d9e-0588f4a5a334.png)

**Comparison between pre and post optimized Models**

|Model|Precision\_train|Recall\_train|F1 Score\_train|Accuracy\_train|ROC AUC Score\_train|Precision\_test|Recall\_test|F1 Score\_test|Accuracy\_test|ROC AUC Score\_test|
|---|---|---|---|---|---|---|---|---|---|---|
|Logistic Regression|0\.139|0\.786|0\.236|0\.751|0\.846|0\.128|0\.758|0\.22|0\.739|0\.84|
|Optimized Logistic Regression|0\.138|0\.797|0\.236|0\.748|0\.846|0\.131|0\.806|0\.225|0\.73|0\.841|
|KNN|0\.3|1\.0|0\.462|0\.886|0\.997|0\.076|0\.29|0\.12|0\.793|0\.635|
|Optimized KNN|0\.336|1\.0|0\.503|0\.903|0\.997|0\.075|0\.242|0\.115|0\.818|0\.614|
|Random Forest|1\.0|1\.0|1\.0|1\.0|1\.0|0\.089|0\.161|0\.115|0\.879|0\.749|
|Optimized Random Forest|1\.0|1\.0|1\.0|1\.0|1\.0|0\.074|0\.081|0\.077|0\.906|0\.755|
|XGBoost|0\.209|0\.904|0\.339|0\.828|0\.94|0\.128|0\.597|0\.211|0\.783|0\.779|
|Optimized XGBoost|0\.22|0\.882|0\.353|0\.842|0\.932|0\.135|0\.613|0\.222|0\.791|0\.788|


![image](https://user-images.githubusercontent.com/50593017/205737955-9bf9e48d-2086-45c5-a582-d0fd594178f2.png)

![image](https://user-images.githubusercontent.com/50593017/205738602-2b249122-f3d4-4092-957d-14c2ee692a11.png)


- Out of the 4 models, the optimized logistic regression model can be selected as best model according to the recall score and ROC score.
- Especially in this project, we are trying to maximize recall score to minimize the risk on patietns.
- The logistic regression models are the ones identified as the minimal overfitting models because their training scores are approximately similar with testing scores.
- The optimized logitic regression model not only gained the highest testing recall score, it also performed very well on testing data over training data according to the recall score.
- Therefore, optimized logistic regression model is the best model to predict the risk of stoke of patients.
