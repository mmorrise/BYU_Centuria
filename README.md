# BYU_Centuria
Kaggle competition with the best team in BYU

#import statements
import csv as csv
import numpy as np
import pandas
from sklearn.ensemble import RandomForestClassifier

def cleanData(data):
    data = data.drop([],1)
    data.fillna(data.mean(), inplace=True)
    
    return data

data = panda.read_csv("train_1.csv")
data = cleanData(data)

target = data.target
train = data[data.columns[2:]]

forest = RandomForestClassifier(200)
forest.fit(train.iloc[:],target.iloc)

test = test_data[test_data.columns[1:]]

prediction = forest.predict_proba(test.iloc[:])

result = prediction[:,1]

output = pandas.DataFrame(result)
