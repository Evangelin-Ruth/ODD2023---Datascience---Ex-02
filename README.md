# Ex02-Outlier

## AIM:
To read a given dataset and remove outliers and save a new dataframe.

## ALGORITHM:

(1) Remove outliers using IQR

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

(i) Using IQR detect weight outliers and print them

(ii) Using IQR, detect height outliers and print them

## PROGRAM:
```
import pandas as pd

import numpy as np

import seaborn as sns

import pandas as pd

from scipy import stats

df = pd.read_csv("/content/heights.csv")

sns.boxplot(data=df)

sns.scatterplot(data=df)

max =df['height'].quantile(0.90)

min =df['height'].quantile(0.15)

max

min

dq = df[((df['height']>=min)&(df['height']<=max))]

dq

low = min-1.5*iqr

high = max+1.5*iqr

dq = df[((df['height']>=min)&(df['height']<=max))]

dq
```
# ZSCORE
```
import pandas as pd

import numpy as np

import seaborn as sns

import pandas as pd

from scipy import stats

data = {'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}

df = pd.DataFrame(data)

df

sns.boxplot(data=df)

z = np.abs(stats.zscore(df))

print(df[z['weight']>3])

val = [12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]

out=[]

def d_o(val):

ts=3

m=np.mean(val)

sd=np.std(val)

for i in val:

z=(i-m)/sd

if np.abs(z)>ts:

  out.append(i)
return out

op = d_o(val)

op
```

## OUTPUT:
![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/9681119d-3cda-4a00-9e43-d469bb268a8c)
![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/6a7e8f88-7e78-4d1c-b90d-4aaa958ed8c5)
![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/71036c30-b07b-45c2-9807-46552c1d4ec0)
![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/53ba2ec4-739c-4b71-9194-24b246412d36)
![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/c2337d7c-ba9f-40ae-8b4b-93ddea1155cd)
![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/f9d0accb-1648-4560-92c7-7577be99baa5)
![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/f370fe9e-9d95-49db-9406-23571a600072)
![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/00e9140a-e9cf-45b8-8725-87fec60d8172)
![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/f9f8556f-35b2-4240-8d9f-0d92828517d1)

## RESULT:
Thus, the given data is read,remove outliers and save a new dataframe was created and executed successfully.











