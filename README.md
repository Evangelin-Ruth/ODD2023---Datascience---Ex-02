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



![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/8c854777-1675-4611-8b14-8451fd5e7069)



![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/ab7611c0-f890-4642-a95a-39d637631fc4)



![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/7df83e36-6d68-456b-ad67-6c8e932a56ae)



![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/5f32440e-4b0e-43c0-9028-5d01364fdb23)


![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/77fdba6f-e09b-4554-ae85-9274ebac500e)

![image](https://github.com/Evangelin-Ruth/ODD2023---Datascience---Ex-02/assets/94219798/bff6f689-ebb6-4be0-b508-ff33effe1610)





## RESULT:
Thus, the given data is read,remove outliers and save a new dataframe was created and executed successfully.











