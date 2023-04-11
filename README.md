# EX-05-Feature-Generation


## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# CODE
```
NAME:S.Prema Latha
REG.NO:212222230112
import pandas as pd
df=pd.read_csv("data.csv")
df

#feature generation
import category_encoders as ce
be=ce.BinaryEncoder()
ndf=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
ndf

ndf2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
ndf2

df1=df.copy()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder,OneHotEncoder
import category_encoders as ce
be=ce.BinaryEncoder()
ohe=OneHotEncoder(sparse=False)
le=LabelEncoder()
oe=OrdinalEncoder()


df1["City"] = ohe.fit_transform(df1[["City"]])

temp=['Cold','Warm','Hot','Very Hot']
oe1=OrdinalEncoder(categories=[temp])
df1['Ord_1'] = oe1.fit_transform(df1[["Ord_1"]])

edu=['High School','Diploma','Bachelors','Masters','PhD']
oe2=OrdinalEncoder(categories=[edu])
df1['Ord_2']= oe2.fit_transform(df1[["Ord_2"]])
df1

#feature scaling
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df2=pd.DataFrame(sc.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df2

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df3=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df3

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df4=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df4

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df5=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df5


Encoading.draw:


import pandas as pd
df=pd.read_csv("Encoding Data.csv")
df

#feature generation
import category_encoders as ce
be=ce.BinaryEncoder()
ndf=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
ndf

ndf2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
ndf2

df1=df.copy()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
le=LabelEncoder()
oe=OrdinalEncoder()

df1["nom_0"] = oe.fit_transform(df1[["nom_0"]])
temp=['Cold','Warm','Hot']
oe2=OrdinalEncoder(categories=[temp])
df1['ord_2'] = oe2.fit_transform(df1[['ord_2']])

df1

#feature scaling
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df0=pd.DataFrame(sc.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df0

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df2=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df2

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df3=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df3

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df4=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df4


Titanic.csv:

import pandas as pd
df=pd.read_csv("titanic_dataset.csv")
df

#removing unwanted data
df.drop("Name",axis=1,inplace=True)
df.drop("Ticket",axis=1,inplace=True)
df.drop("Cabin",axis=1,inplace=True)

#data cleaning
df.isnull().sum()

df["Age"]=df["Age"].fillna(df["Age"].median())
df["Embarked"]=df["Embarked"].fillna(df["Embarked"].mode()[0])

df.isnull().sum()

df

#feature encoding

from category_encoders import BinaryEncoder
be=BinaryEncoder()
df["Sex"]=be.fit_transform(df[["Sex"]])
ndf=be.fit_transform(df["Sex"])
ndf

df1=df.copy()
from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
embark=['S','C','Q']
e1=OrdinalEncoder(categories=[embark])
df1['Embarked'] = e1.fit_transform(df[['Embarked']])
df1

#feature scaling
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df2=pd.DataFrame(sc.fit_transform(df1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df2

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df3=pd.DataFrame(sc1.fit_transform(df1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df3

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df4=pd.DataFrame(sc2.fit_transform(df1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df4

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df5=pd.DataFrame(sc3.fit_transform(df1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df5
```


# OUPUT
![image](https://user-images.githubusercontent.com/120620842/231096402-bc43e4f5-b7e4-43d4-8041-d238e245a091.png)
![image](https://user-images.githubusercontent.com/120620842/231096469-82d6e2ef-5874-4bd0-bdd9-d57044b9268f.png)
![image](https://user-images.githubusercontent.com/120620842/231096523-8fc43b2e-2ad8-4e0d-91e1-3b8674f730af.png)
![image](https://user-images.githubusercontent.com/120620842/231096585-b54491ea-ebf3-4ddb-b7fc-8e6258195749.png)
![image](https://user-images.githubusercontent.com/120620842/231096673-8312bd53-5d2f-4fc8-ba95-2a23390996dc.png)
![image](https://user-images.githubusercontent.com/120620842/231096755-04080646-0307-4f6b-9ee6-f6d8d366335e.png)
![image](https://user-images.githubusercontent.com/120620842/231096812-1766ce92-dee6-46c7-8ea1-c1a5a74b9c42.png)
![image](https://user-images.githubusercontent.com/120620842/231096874-7d232dd2-6832-4aba-9e63-43d644fdcbef.png)
![image](https://user-images.githubusercontent.com/120620842/231096935-2f90f1f5-98ad-4418-8630-c6502c3f9287.png)
![image](https://user-images.githubusercontent.com/120620842/231096982-c75bfaf1-330d-4ca8-be9a-0bc36ab8c84e.png)
![image](https://user-images.githubusercontent.com/120620842/231097029-5c310ac3-29e0-415e-8848-68b042b6ccb3.png)
![image](https://user-images.githubusercontent.com/120620842/231097073-1e562d94-03a6-4f72-ae89-49293f9c7134.png)
![image](https://user-images.githubusercontent.com/120620842/231097296-9577a3d6-37c2-425e-aa26-41b26549725b.png)
![image](https://user-images.githubusercontent.com/120620842/231097352-4af0a987-1765-4bf8-a296-307defd3b7f1.png)
![image](https://user-images.githubusercontent.com/120620842/231097469-cfa6db4a-16b3-416d-96e3-4de94b6509a1.png)
![image](https://user-images.githubusercontent.com/120620842/231097521-2e209bd4-4497-4b43-85c4-8a2f122bdc35.png)
![image](https://user-images.githubusercontent.com/120620842/231097574-9b78fc16-819c-4e11-b746-78fc8e8d6e0d.png)
![image](https://user-images.githubusercontent.com/120620842/231097664-a4e7045d-c022-40f2-83f1-cbb22eaabd71.png)
![image](https://user-images.githubusercontent.com/120620842/231097738-b478c20e-923e-4435-9d38-a21dc6b64bb2.png)
![image](https://user-images.githubusercontent.com/120620842/231097847-09af008e-2f7c-43c3-a0e1-52fa6185faac.png)
![image](https://user-images.githubusercontent.com/120620842/231097984-f0ce235e-ede1-4d24-842b-8394922e53b4.png)
![image](https://user-images.githubusercontent.com/120620842/231098043-16b375ae-da98-484b-9fa0-ca61eb76ba7a.png)
![image](https://user-images.githubusercontent.com/120620842/231098092-ed9ce444-08d6-410d-b57c-34a7651da0c0.png)

# RESULT:

Feature Generation process and Feature Scaling process is applied to the given data frames sucessfully

