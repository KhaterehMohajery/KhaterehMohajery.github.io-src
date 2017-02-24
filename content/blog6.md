Title: Useful Tricks in Pandas
Date: 2017-01-12 10:20
Category: Review

In this blog post I want to introduce some useful and handy pandas tricks that have made my life much easier in several occasions (I will add to this as I encounter a new useful method or trick). 

1- Getting all the unique values in a column of a dataframe by using:
``` python
df.columnname.unique()
```
2- Getting the number of null values for the data frame or the number or proportion of null values for each column:
``` python
df.isnull().sum()
```
And for each column:
``` python
df.columnname.isnull().sum()
df.columnname.isnull().mean()
```
3- Mapping trick:
First you create a mapping dictionary:
``` python
equiv = {"a":1, "b":2, "c":3} 
```
Then you map for example a column to it
``` python
df = pd.DataFrame( {"A": ["a", "b", "c"]} ) 
df["B"] = df["A"].map(equiv)
print(df) 
  A B 
0 a 1
1 b 2 
2 c 3
```
4- Getting dummy variables for categorical variables and adding it to the same data frame in one step:
``` python
data = {'name': ['Jason', 'Amy', 'Tina', 'Jason', 'Amy'], 
'sex': ['male', 'female', 'female', 'male', 'female'],
'age':[17,18,25,21,19]}
df = pd.DataFrame(data, columns = ['name', 'sex'])

df = pd.concat([df, pd.get_dummies(df[['name','sex']])], axis=1)
```
5- Sometimes, you need to make categorical variables into integer categories. This can be done by using  Labelencoder 
from sklearn preprocessing library:
``` python
from sklearn.preprocessing import LabelEncoder
```
Applying on above data frame the column “sex” can be converted 0 for male and 1 for female:
``` python
LabelEncoder().fit_transform(df.sex)
```
6- For applying a condition on all values of a row, np.where can be used. For example:
``` python
df.sex = np.where (df.sex.str.contains('fe') == True ,'Female', df.sex)
``` 
Each row that contains string 'fe', it puts in 'Female'. Otherwise, it leaves it as is.

7- If you need a new data frame after applying  groupby method, putting option as_index =False  results in returning a data frame:
``` python
df = df.groupby('sex', as_index =False).age.mean()
  sex    age
0 female 20.666667
1 male   19.000000

```




