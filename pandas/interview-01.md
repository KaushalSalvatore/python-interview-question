#### Q.1 Mention the different types of Data Structures in Pandas ? 
```bash
Series - It is a one-dimensional array-like structure with homogeneous data which means data of
different data types cannot be a part of the same series. It can hold any data type such as integers, 
floats, and strings
DataFrame - It is a two-dimensional array-like structure with heterogeneous data. It can contain 
data of different data types and the data is aligned in a tabular manner.
Panel - The Pandas have a third type of data structure known as Panel, which is a 3D data structure 
capable of storing heterogeneous data but it isn’t that widely used.

A Series is a one-dimensional data structure in pandas, whereas the DataFrame is the two-dimensional 
data structure in pandas.

import pandas as pd

# a simple dictionary
dict = {'A': 101,
		'B': 202,
		'C': 303}

# create series from dictionary
ser = pd.Series(dict)
Output:

A    101
B    202
C    303
```

#### Q.2 How can we convert Series to DataFrame ? 
```bash
Series.to_frame(name=None)
```

#### Q.3 Define the different ways a DataFrame can be created in pandas ? 
```bash
import pandas as pd    
a = ['Python', 'Pandas']    
info = pd.DataFrame(a)    
print(info)    
```

#### Q.4 How will you add a column to a pandas DataFrame ? 
```bash
import pandas as pd      
info = {'one' : pd.Series([1, 2, 3, 4, 5], index=['a', 'b', 'c', 'd', 'e']),    
        'two' : pd.Series([1, 2, 3, 4, 5, 6], index=['a', 'b', 'c', 'd', 'e', 'f'])}    

info['three']=pd.Series([20,40,60],index=['a','b','c'])    
print (info)   
```

#### Q.5 How to Delete Index, Rows or Columns From a Pandas Data Frame ? 
```bash
del df.index.name

drop() (0 if it indicates the rows and 1 if it drops the columns.)

df.drop_duplicates() (we can remove duplicate rows from the DataFrame.)

DataFrame.drop(['Column_Name'], axis=1)
```

#### Q.6  How to Rename the Index or Columns of a Pandas DataFrame ? 
```bash
You can use the .rename method to give different values to the columns or the index values of DataFrame.

DataFrame.rename(columns={'column1': 'COLUMN_1', 'column2':'COLUMN_2'}, inplace=True)

DataFrame.set_axis(labels=['COLUMN_1','COLUMN_2'], axis=1, inplace=True)
```

#### Q.7  How to get the items of series A not present in series B ? 
```bash
import pandas as pd  
p1 = pd.Series([2, 4, 6, 8, 10])  
p2 = pd.Series([8, 10, 12, 14, 16])  
p1[~p1.isin(p2)] 
p_u = pd.Series(np.union1d(p1, p2))  # union  
p_i = pd.Series(np.intersect1d(p1, p2))  # intersect  
```

#### Q.8 How can we convert DataFrame,series into a NumPy array ? 
```bash
DataFrame.to_numpy(dtype=None, copy=False)  
```

#### Q.9 What is Data Aggregation ? 
```bash
sum: It is used to return the sum of the values for the requested axis.
min: It is used to return a minimum of the values for the requested axis.
max: It is used to return a maximum values for the requested axis.
```

#### Q.10 How to access the first few rows of a dataframe ? 
```bash
df.head(n)

df.iloc[:n]
```

#### Q.11 How to add an Index, Row, or Column to an Existing Dataframe ? 
```bash
Pandas set_index() is a function for modifiying the index of a data frame from a data frame, series,
or list. The index column can also be set while creating a data frame. However, because a data frame 
might be made up of two or more data frames, the index can be altered later using this method.

df.set_index(keys, drop=True, append=False, inplace=False, verify_integrity=False)
DataFrame.loc[Row_Index]=new_row
pandas.concat([Dataframe1,Dataframe2])
```

#### Q.12 How to Compute Mean, Median, Mode, Variance, Standard Deviation, and Various Quantile Ranges in Pandas ? 
```bash
DataFrame.mean(): To calculate the mean
DataFrame.median(): To calculate median
DataFrame.mode(): To calculate the mode
DataFrame.var(): To calculate variance
DataFrame.std(): To calculate the standard deviation
DataFrame.quantile(): To calculate quantile range, with range value as a parameter
```

#### Q.13 How to Sort a Dataframe ? 
```bash
DataFrame.sort_values(by='Age',ascending=True)
```

#### Q.14 How to Check and Remove Duplicate Values in Pandas ? 
```bash
DataFrame.duplicated()
DataFrame.drop_duplicates()
```

#### Q.15 How to Handle Missing Data in Pandas ? 
```bash
isnull(): It returns True for NaN values or null values and False for present values
notnull(): It returns False for NaN values and True for present values
dropna(): It analyzes and drops Rows/Columns with Null values
fillna(): It let the user replace NaN values with some value of their own
replace(): It is used to replace a string, regex, list, dictionary, series, number, etc.
interpolate(): It fills NA values in the dataframe or series.
```

#### Q.16 What is groupby() Function in Pandas ? 
```bash
DataFrame.groupby(by=['Col_name'])
DataFrame.groupby(by=None, axis=0, level=None, as_index=True, sort=True, group_keys=True, 
squeeze=False, **kwargs)
```

#### Q.17 What are loc and iloc methods in Pandas ? 
```bash
Dataframe.[]: This function is also known as the indexing operator
Dataframe.loc[]: This function is used for label-based indexing.
Dataframe.iloc[]: This function is used for positions or integer-based indexing.
```

#### Q.18 Difference between the interpolate() and fillna() ? 
```bash
The interpolate() and fillna() methods in pandas are used to handle missing or NaN (Not a Number) 
values in a DataFrame or Series.

new_df = df['column_name'].fillna(value,inplace=true)
```

#### Q.19 Explain about Data operations in Pandas ? 
```bash
isnull(): isnull 's job is to return true if either of the rows have null values.
notnull(): It is the inverse of the isnull() function, returning true values for non-null values.
dropna(): This function evaluates and removes null values from rows and columns.
fillna(): It enables users to substitute other values for the NaN values.
replace(): It's a powerful function that can take the role of a regex, dictionary, string,  series,  and more.
interpolate(): It's a useful function for filling null values in a series or data frame.

lower(): Any strings in the  index or series are converted to lowercase letters.
upper(): Any strings in the  index or series are converted to uppercase letters.
strip(): This method eliminates spacing from every string in the Series/index, along with a new line.
split(' '): It's a method that separates a string according to a pattern.
cat(sep=' '): With a defined separator, it concatenates series/index items.
contains(pattern): If a substring is available in the current element, it returns True; otherwise, 
it returns False.
replace(a,b): It substitutes the value b for the value a.
repeat(value): Each element is repeated a defined multiple times.
count(pattern): It returns the number of times a pattern appears in each element.
startswith(pattern): If all of the components in the series begin with a pattern, it returns True.
endswith(pattern): If all of the components in the series terminate in a pattern, it returns True.
find(pattern): It can be used to return the pattern's first occurrence.
findall(pattern): It gives you a list of all the times the pattern appears.
swapcase: It is used to switch the lower/upper case.
islower(): If all of the characters in the Series/Index string are lowercase, it returns True. 
Otherwise, False is returned.
isupper(): If all of the characters in the Series/Index string are uppercase, it returns True.
 Otherwise, False is returned.
isnumeric(): If all of the characters in the Series/Index string are numeric, it returns True.
 Otherwise, False is returned.
```

#### Q.20 create xml file with datafrane ? 
```bash
import pandas as pd
df = pd.DataFrame({
    'Name': ['Alice', 'Bob'],
    'Age': [25, 30],
    's.No': ['Engineer', 'Doctor']
})
df.to_xml("sample_data.xml")
```