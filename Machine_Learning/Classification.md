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
