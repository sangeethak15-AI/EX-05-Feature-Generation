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

# 1.FEATURE GENERATION FOR Data.csv
## CODE FOR FEATURE ENCODING AND FEATURE SCALING:
```
import pandas as pd
df=pd.read_csv("data.csv")
df
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
temp=["Cold","Warm","Hot","Very Hot"]
enc=OrdinalEncoder(categories=[temp])
df["Ord_1"]=enc.fit_transform(df[["Ord_1"]])
df
education=["High School","Diploma","Bachelors","Masters","PhD"]
ed=OrdinalEncoder(categories=[education])
df["Ord_2"]=ed.fit_transform(df[["Ord_2"]])
df
pip install category_encoders
from category_encoders import BinaryEncoder
be=BinaryEncoder()
be.fit_transform(df["bin_1"])
df["bin_1"]=be.fit_transform(df[["bin_1"]])
df
be1=BinaryEncoder()
be1.fit_transform(df["bin_2"])
df["bin_2"]=be1.fit_transform(df[["bin_2"]])
df
from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse=False)
ohe.fit_transform(df[["City"]])
from category_encoders import TargetEncoder
te=TargetEncoder()
te.fit_transform(X=df['Ord_1'],y=df["Target"])
le=LabelEncoder()
df["City"]=le.fit_transform(df[["City"]])
df

from sklearn.preprocessing import StandardScaler
sc=StandardScaler()
df1=pd.DataFrame(sc.fit_transform(df),columns=['id','bin_1','bin_2','City','Ord_1','Ord_2','Target'])
df1

from sklearn.preprocessing import MaxAbsScaler
mas=MaxAbsScaler()
df2=pd.DataFrame(mas.fit_transform(df),columns=['id','bin_1','bin_2','City','Ord_1','Ord_2','Target'])
df2

from sklearn.preprocessing import MinMaxScaler
mms=MinMaxScaler()
df3=pd.DataFrame(mms.fit_transform(df),columns=['id','bin_1','bin_2','City','Ord_1','Ord_2','Target'])
df3

from sklearn.preprocessing import RobustScaler
rs=RobustScaler()
df4=pd.DataFrame(rs.fit_transform(df),columns=['id','bin_1','bin_2','City','Ord_1','Ord_2','Target'])
df4
```
# OUTPUT
### Given DataFrame
![1 give](https://user-images.githubusercontent.com/93992063/166719292-a8424793-bd26-4f55-8abe-8cf44aa14f80.png)

## Feature encoding using Ordinal Encoder
![1 ori](https://user-images.githubusercontent.com/93992063/166719564-dc9baa53-656c-4234-a666-12f180ca4af3.png)
![1 ori(](https://user-images.githubusercontent.com/93992063/166719752-5a370928-fed2-4744-96b2-e6f75f71aaed.png)
## Feature encoding using Binary Encoder
![1 bin](https://user-images.githubusercontent.com/93992063/166720022-d841f3f7-f23f-4540-84be-33619b86d7ff.png)
![1 bin(](https://user-images.githubusercontent.com/93992063/166720183-5e234f23-1fb2-470b-bd8a-ae12dcbb1b96.png)

## Feature encoding using One Hot Encoder
![1 onehot](https://user-images.githubusercontent.com/93992063/166720383-aa50fbe0-1cc0-41fd-a2a7-03ab58311e83.png)

## Feature encoding using Target Encoder
![1 tar](https://user-images.githubusercontent.com/93992063/166720529-b4a85e7a-8732-4248-9a88-d1e715a78a20.png)

## Feature encoding using Label Encoder
![1 last](https://user-images.githubusercontent.com/93992063/166720708-61c8afea-768e-41d9-82fc-0af3b58a493d.png)

## Feature scaling using Standard Scaler
![1 stand](https://user-images.githubusercontent.com/93992063/166720867-3074ad4c-7272-4ea0-9bc7-41c4e7e95cd0.png)

## Feature scaling using Robust Scaler
![1 rob](https://user-images.githubusercontent.com/93992063/166721234-6fdd3be4-3a8a-4441-9cc7-a62f5fe9f23b.png)

## Feature scaling using MaxAbs Scaler
![1 max](https://user-images.githubusercontent.com/93992063/166721264-19cf4da1-8ccc-4914-87f8-1604c9b4b9b0.png)

## Feature scaling using MinMax Scaler
![1 min](https://user-images.githubusercontent.com/93992063/166721297-48b20bb1-803f-4d19-bf6e-a07691deec09.png)

# 2.FEATURE GENERATION FOR Encoding.csv
## CODE FOR FEATURE ENCODING AND FEATURE SCALING:
```
import pandas as pd

df=pd.read_csv("Encoding Data.csv")
df
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
temp=["Cold","Warm","Hot"]
enc=OrdinalEncoder(categories=[temp])
df["ord_2"]=enc.fit_transform(df[["ord_2"]])
df
from category_encoders import BinaryEncoder
be=BinaryEncoder()
df['bin_1']=be.fit_transform(df[['bin_1']])
df
be1=BinaryEncoder()
df['bin_2']=be1.fit_transform(df[['bin_2']])
df
from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse=False)
ohe.fit_transform(df[["nom_0"]])
le=LabelEncoder()
df["nom_0"]=le.fit_transform(df[["nom_0"]])
df

from sklearn.preprocessing import StandardScaler
sc=StandardScaler()
df1=pd.DataFrame(sc.fit_transform(df),columns=['id','bin_1','bin_2','nom_0','Ord_2'])
df1

from sklearn.preprocessing import MinMaxScaler
mms=MinMaxScaler()
df2=pd.DataFrame(mms.fit_transform(df),columns=['id','bin_1','bin_2','nom_0','Ord_2'])
df2

from sklearn.preprocessing import MaxAbsScaler mas=MaxAbsScaler()
df3=pd.DataFrame(mas.fit_transform(df),columns=['id','bin_1','bin_2','nom_0','Ord_2'])
df3

from sklearn.preprocessing import RobustScaler
rs=RobustScaler()
df4=pd.DataFrame(rs.fit_transform(df),columns=['id','bin_1','bin_2','nom_0','Ord_2'])
df4
```
# OUTPUT
## Given DataFrame
![2 give](https://user-images.githubusercontent.com/93992063/166725050-c888dd47-1095-4dcb-bc57-bb576a1a054d.png)

## Feature encoding using Ordinal Encoder
![2 ori](https://user-images.githubusercontent.com/93992063/166725173-657f006a-bb08-4a10-98fc-ebcddcaef440.png)

## Feature encoding using Binary Encoder
![2 bin](https://user-images.githubusercontent.com/93992063/166725300-f2ab5620-c2cb-4c97-a30b-683f61b2b325.png)

## Feature encoding using One Hot Encoder
![2 oneshot](https://user-images.githubusercontent.com/93992063/166725927-62709ef8-e22f-4666-b8bf-cf0be6931af7.png)

## Feature scaling using Standard Scaler
![2 stand](https://user-images.githubusercontent.com/93992063/166726434-a6ced112-ebfa-4602-ba4d-f09c8204d92e.png)

## Feature scaling using Robust Scaler
![2 rob](https://user-images.githubusercontent.com/93992063/166726654-a9f9b879-d54a-4c4f-a0bc-8425aa7f8235.png)

## Feature scaling using MaxAbs Scaler
![2 max](https://user-images.githubusercontent.com/93992063/166726680-7e8871dd-1f5b-4702-bef3-1c64ed909b59.png)

## Feature scaling using MinMax Scaler
![2 min](https://user-images.githubusercontent.com/93992063/166726706-871f0ca9-14a8-4cb4-988c-1e7f779230e4.png)

# 3.FEATURE GENERATION FOR titanic_dataset.csv
## CODE FOR FEATURE ENCODING AND FEATURE SCALING:
```
import pandas as pd
df=pd.read_csv("titanic_dataset.csv")
df
df.isnull().sum()
df["Age"]=df["Age"].fillna(df["Age"].median())
df["Embarked"]=df["Embarked"].fillna(df["Embarked"].mode()[0])
df
df.drop("Cabin",axis=1,inplace=True)
df.drop("Ticket",axis=1,inplace=True)
df.drop("Name",axis=1,inplace=True)
df.isnull().sum()
df
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
embark=["C","S","Q"]
emb=OrdinalEncoder(categories=[embark])
df["Embarked"]=emb.fit_transform(df[["Embarked"]])
df
from category_encoders import BinaryEncoder
be=BinaryEncoder()
df["Sex"]=be.fit_transform(df[["Sex"]])
df

from sklearn.preprocessing import StandardScaler
ss=StandardScaler()
df1=pd.DataFrame(ss.fit_transform(df),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked','PClass'])
df1

from sklearn.preprocessing import MinMaxScaler
mms=MinMaxScaler()
df2=pd.DataFrame(mms.fit_transform(df),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked','PClass'])
df2

from sklearn.preprocessing import MaxAbsScaler
mas=MaxAbsScaler()
df3=pd.DataFrame(mas.fit_transform(df),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked','PClass'])
df3

from sklearn.preprocessing import RobustScaler
rs = RobustScaler()
df4=pd.DataFrame(rs.fit_transform(df),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked','PClass'])
df4
```
# OUTPUT
## Given DataFrame
![3 give](https://user-images.githubusercontent.com/93992063/166727067-24cde20a-c113-4c23-857e-97aafe8c189f.png)

## Resolving null value data
![3 null](https://user-images.githubusercontent.com/93992063/166727115-dae8beac-d1a4-4820-95f5-86ee0876e997.png)
## Dropping unnecessary columns
![3 rr](https://user-images.githubusercontent.com/93992063/166727163-aa48c26f-2e5a-47b8-8891-098baf71e92a.png)

## Feature encoding using Ordinal Encoder
![3 ori](https://user-images.githubusercontent.com/93992063/166727663-28c2d69f-3caa-4d9d-a47d-f0ca93ec7eb8.png)

## Feature encoding using Binary Encoder
![3 bin](https://user-images.githubusercontent.com/93992063/166727700-10b9c5bf-6ce8-449b-ba84-1233effacfea.png)

## Feature scaling using Standard Scaler
![3 stand](https://user-images.githubusercontent.com/93992063/166727799-cec61d91-67b3-41ae-b0e8-888a00e9ef05.png)

## Feature scaling using Robust Scaler
![3 rob](https://user-images.githubusercontent.com/93992063/166727839-b57ed25b-ccfa-47c7-99fe-eac659753e29.png)

## Feature scaling using MaxAbs Scaler
![3 max](https://user-images.githubusercontent.com/93992063/166727890-bbcc31f5-a0eb-47eb-a237-28b5d7cd97e9.png)

## Feature scaling using MinMax Scaler
![3 min](https://user-images.githubusercontent.com/93992063/166727936-24639817-1c3d-43eb-ab1b-be1450241d46.png)

# RESULT:
Feature Encoding process and Feature Scaling process is applied to the given data frame sucessfully.
