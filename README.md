# California-Housing-Prices
Predicting the Value of houses in California
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import sklearn


DF_train=pd.read_csv('C:/Users/C5257796/Desktop/ML projects/California housing prices/housing.csv')

DF_train.head()

DF_train.columns

def merge_two_dict(x,y):
    z=x.copy()
    z.update(y)
    return z

dict={}
list_ocean_proximity=list(set(DF_train['ocean_proximity']))
for i in range(len(list_ocean_proximity)):
    dict= merge_two_dict(dict,{str(list_ocean_proximity[i]):i})

print(dict)

DF_train['ocean_proximity']=DF_train['ocean_proximity'].map(dict)
DF_train['ocean_proximity']

DF_train.info()

DF_train.hist(bins=90,figsize=(30,30))
plt.show()



