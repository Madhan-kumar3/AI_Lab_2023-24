# Ex.No: 13 Learning – Use Supervised Learning  
### DATE: 28.10.2023                                                                        
### REGISTER NUMBER : 21222106206
### AIM: 
To write a program to train the classifier for Predicting the Placement Status of Students.

### Program:
```
import pandas as pd
data=pd.read_csv('/content/Placement_Data (1).csv')
print("Placement data")
data.head()

data1=data.copy()
data1=data1.drop(["sl_no","salary"],axis=1)
print("Salary data")
data1.head()

print("Checking the null() function")
data1.isnull().sum()

print("Data Duplicate")
data1.duplicated().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data1["gender"]=le.fit_transform(data1["gender"])
data1["ssc_b"]=le.fit_transform(data1["ssc_b"])
data1["hsc_b"]=le.fit_transform(data1["hsc_b"])
data1["hsc_s"]=le.fit_transform(data1["hsc_s"])
data1["degree_t"]=le.fit_transform(data1["degree_t"])
data1["workex"]=le.fit_transform(data1["workex"])
data1["specialisation"]=le.fit_transform(data1["specialisation"])
data1["status"]=le.fit_transform(data1["status"])
print("Print data")
data1

x=data1.iloc[:,:-1]
print("Data-status")
x

y=data1["status"]
print("data-status")
y


from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)

from sklearn.linear_model import LogisticRegression
lr=LogisticRegression(solver="liblinear")
lr.fit(x_train,y_train)
y_pred=lr.predict(x_test)
print("y_prediction array")
y_pred

from sklearn.metrics import accuracy_score
accuracy=accuracy_score(y_test,y_pred)
print("Accuracy value")
accuracy

from sklearn.metrics import confusion_matrix
confusion = confusion_matrix(y_test,y_pred)
print("Confusion array")
confusion

from sklearn.metrics import classification_report
classification_report1 = classification_report(y_test,y_pred)
print("Classification report")
print(classification_report1)

print("Prediction of LR")
lr.predict([[1,80,1,90,1,1,90,1,0,85,1,85]])
```

### Output:
1. Placement data
2. Salary data
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/100289733/004c0d4b-0d2b-4bd2-9749-f85a67e09b21)
3. Checking the null function()
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/100289733/57785558-a3c3-4ec4-b3df-a1eea1b5d1c8)
4. Data duplicate 
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/100289733/b243d88d-c465-45ad-bcf0-48e37d5b94c3)
5. Print data
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/100289733/d3d90792-a7a7-4767-9e56-69297cc34224)
6. Data status 
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/100289733/01e33a84-a060-4d15-a693-77c461480cac)
7. y_prediction array
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/100289733/24b49a1a-a977-4f85-ba70-725ed9a5a8da)
8. Accuracy value
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/100289733/7191b42e-4691-4236-b580-7398bfcc796d)
9. Confusion matrix
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/100289733/e2451f20-84d0-407f-ad0b-0ac455983efe)
10. Classification report
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/100289733/6417878f-3c1d-475b-a417-0716c0cf8794)
11. Prediction of LR
![image](https://github.com/Jai-Pradhiksha/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/100289733/16349aca-e50c-4f59-abcf-6b3469c1d7e7)

### Result:
Thus the system was trained successfully and the prediction was carried out.
