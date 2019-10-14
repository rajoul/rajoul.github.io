### Classification
classification is a supervised learning approach in which the computer program learns from the data input given to it and then
uses this learning to classify new observation.The goal is to predict discrete values, e.g. {1,0},{True,False},{spam,not spam}.
I am going to work on titanic dataset where the goal is to predict if a person hanving a name,age,Pclass,Cabin is been survived
or not.So the target is survived (O if no,1 if yes).I am going to treat our dataset with :
# Logistic regression:
first,I import sklearn and necessary modules
```
import pandas as pd
import numpy as np
from sklearn.model_selection import cross_val_score, train_test_split
from sklearn.metrics import classification_report, confusion_matrix
from sklearn.model_selection import cross_val_score, train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import RandomizedSearchCV
from sklearn.ensemble import RandomForestRegressor

import my_package.models.models as md
import my_package.preprocessing_data.preprocessing as prepro
import my_package.preprocessing_data.discovery as ds
```
I load titanic dataset
```
train = pd.read_csv("data/train.csv", sep=',')
train.head()
```
<p align="center">
  <img src="https://rajoul.github.io/Machine_Learning/image/head.png" width="400" height="300">
</p>
I clean my dataset from NAN value and replace undesired characters
```
def variable_manquante(model):
    tab=[]
    for ele in model.columns:
        if True in list(model[ele].isnull().unique()):
            tab.append(ele)     
    return tab
def remplace_mode_mediane(df,columnName) :
    valeur=''
    if df[columnName].dtype in ['float64','int64','float32','int32']:
        x = df[columnName].median()
        valeur=x
    else :
        x = df[columnName].mode()
        valeur=x[0]
        
    for index, row in df.iterrows() :
        if pd.isna(row[columnName]) :
            df.loc[index,columnName] = valeur
def replace_all_nan(model,tableau):
	for ele in tableau:
		remplace_mode_mediane(model,ele)
def replace_virg_point(model,column,typ):
	model[column]=model[column].str.replace(',','.').astype(typ)
nan=ds.variable_manquante(train) # return a tableau des variables that contain NAN value
prepro.replace_all_nan(train,nan)
train.head()
```
<p align="center">
  <img src="https://rajoul.github.io/Machine_Learning/image/clean.png" width="400" height="300">
</p>
after cleaning process,dummifying is coming
```
def dumify(X,to_dummify):
    return pd.get_dummies(X, columns=to_dummify)
print("###################################")
print("### dumifying.............. #######")
print("###################################")
print('------------------ADD NEW FEATURE AGE --------')
train['new_age']=train['Age']<10
feature_col=['SibSp', 'Parch', 'Fare','Pclass']
to_dummify=['Pclass']
to_predict=['Survived']
feature_col.append('new_age')
to_dummify.append('new_age')
y=train[to_predict]
X=train[feature_col]
X=dumify(X,to_dummify)
X.head()
```
<p align="center">
  <img src="https://rajoul.github.io/Machine_Learning/image/dummify.png" width="400" height="300">
</p>










