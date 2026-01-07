#### Q.1 How will you combine different Data Frames in Panda ? 
```bash
df1.append(df2)
pd.concat([df1, df2]) 
df1.join(df2)
```

#### Q.2 Pandas library is used for which purpose ? 
```bash
1. Merging and joining Statistical
2. analysis Data
3. normalization Data
4. filling Data
5. cleansing Data
6. inspection Loading and saving data
7. Data visualization
```

#### Q.3 How can we convert Series to DataFrame ? 
```bash
The conversion of Series to DataFrame is quite a simple process. All we need to do is 
to use the to_frame() function.
Series.to_frame(name=None)
```

#### Q.4  How can we convert DataFrame to Numpy Array ? 
```bash
In order to convert DataFrame to a Numpy array we need to use DataFrame.to_numpy() method.
DataFrame.to_numpy(dtype=None, copy=False, na_value=_NoDefault.no_default)
```

#### Q.5 What’s the difference between pivot_table() and groupby() ? 
```bash
Both pivot_table() and groupby() are used to aggregate your dataframe. The major difference is 
in the shape of the result.

import pandas as pd

student_dict = {'Name': ['Kate', 'Harry', 'Sheila'], 'Age': [10, 14, 12], 'Marks': [85, 77, 91]}
 
df = pd.DataFrame(student_dict)
print(df)
table = pd.pivot_table(df, index =['Name', 'Age'])
print(table)

output : 
     Name  Age  Marks
0    Kate   10     85
1   Harry   14     77
2  Sheila   12     91
            
       Name   Age       
Harry  14      77
Kate   10      85
Sheila 12      91
```

#### Q.6 join , merge and concat ? 
```bash
join(): it combines two DataFrames by index.
merge(): it combines two DataFrames by the column or columns you specify.
concat(): it combines two or more DataFrames vertically or horizontally.

df1.merge(df2, on='key', how='inner')
df1 = pd.DataFrame({'ID': [1, 2, 3], 'Name': ['Alice', 'Bob', 'Charlie']})
df2 = pd.DataFrame({'ID': [1, 2, 4], 'Age': [25, 30, 35]})

merged_df = df1.merge(df2, on='ID', how='inner')

df1.join(df2, on='key', how='left')
df1 = pd.DataFrame({'ID': [1, 2, 3], 'Name': ['Alice', 'Bob', 'Charlie']})
df2 = pd.DataFrame({'Age': [25, 30, 35]}, index=[1, 2, 3])

joined_df = df1.join(df2)
```

#### Q.7 dataframe column data count ? 
```bash
import pandas as pd 
data  = pd.read_csv('data.csv')
df = pd.DataFrame(data)

row_count = df['dept'].value_counts(normalize=True) // this will give value in parsentage

row_count = df['dept'].value_counts()['D1'] // D1 column value 

row_count = df['dept'].value_counts() // all column value value

row_count = df.groupby('dept').size()['D1'] // 

row_count = df['dept'].sum()
```

#### Q.8 What is a MultiIndex in Pandas? How do you work with it ? 
```bash
A MultiIndex in Pandas allows you to work with multiple levels of indexing in a DataFrame. 
This is useful for representing hierarchical data, where each index can have multiple levels.
df = pd.DataFrame({
    'Region': ['North', 'North', 'South', 'South'],
    'City': ['New York', 'Boston', 'Chicago', 'Miami'],
    'Sales': [100, 200, 300, 400]
})

df.set_index(['Region', 'City'], inplace=True)
print(df)
```

#### Q.9 What is the cut() function used for in Pandas ? 
```bash
The cut() function is used to segment and sort data values into discrete bins or intervals. 
This is useful for converting continuous data into categorical data by grouping values into bins.

pd.cut(data, bins)
df = pd.DataFrame({'Age': [22, 25, 30, 35, 40, 45]})

# Define bins for age groups
bins = [20, 30, 40, 50]

# Cut the data into bins
df['Age_Group'] = pd.cut(df['Age'], bins)
print(df)

o/p 
  Age    Age_Group
0   22   (20, 30]
1   25   (20, 30]
2   30   (30, 40]
3   35   (30, 40]
4   40   (40, 50]
5   45   (40, 50]
```

#### Q.10 How can you sample random rows from a DataFrame ? 
```bash
df.sample(n=number_of_rows)
```

#### Q.11 How do you perform string operations in Pandas ? 
```bash
import pandas as pd

df = pd.DataFrame({
    'Name': ['Alice', 'Bob', 'Charlie', 'David']
})

# Convert all names to uppercase
df['Name_upper'] = df['Name'].str.upper()

# Check if a name contains the letter 'a'
df['Contains_a'] = df['Name'].str.contains('a')

print(df)

str.lower(): Converts strings to lowercase.
str.len(): Returns the length of each string.
str.replace(): Replaces a substring within the string.
str.startswith(): Checks if the string starts with a specific prefix.
```

#### Q.12  What is the difference between pivot() and melt() functions in Pandas ? 
```bash
pivot(): The pivot() function is used to reshape data by turning unique values from one 
column into separate columns. It is typically used when you want to "spread" a column's 
values into multiple columns.

df = pd.DataFrame({
    'Date': ['2023-01-01', '2023-01-02', '2023-01-01', '2023-01-02'],
    'City': ['New York', 'New York', 'Boston', 'Boston'],
    'Temperature': [30, 32, 25, 28]
})

pivot_df = df.pivot(index='Date', columns='City', values='Temperature')
print(pivot_df)

o/p
City          Boston  New York
Date                          
2023-01-01     25        30
2023-01-02     28        32

melt(): The melt() function is the inverse of pivot(). It "unpacks" a DataFrame and converts it 
from a wide format to a long format by gathering columns into a single column.Example of melt():

df_melted = pivot_df.reset_index().melt(id_vars='Date', value_vars=['Boston', 'New York'], 
var_name='City', value_name='Temperature')
print(df_melted)

       Date     City  Temperature
0  2023-01-01   Boston           25
1  2023-01-02   Boston           28
2  2023-01-01  New York           30
3  2023-01-02  New York           32
```

#### Q.13 How can the standard deviation be calculated from the Series ? 
```bash
import pandas as pd
data = pd.Series([1, 2, 3, 4, 5])
std_deviation = data.std()
```

#### Q.14 Reading Data From a Database Using Pandas ? 
```bash
A database driver (e.g., psycopg2 for PostgreSQL, pymysql for MySQL, sqlite3 built-in)
SQLAlchemy connection string
import pandas as pd
from sqlalchemy import create_engine

engine = create_engine("mysql+pymysql://user:password@host:3306/dbname")

df = pd.read_sql("SELECT * FROM employees", engine)
print(df.head())
```

#### Q.15 Explain the difference between a Pandas Series and a DataFrame ? 
```bash
Series:

One-dimensional labeled array.
Homogeneous data (all elements are of the same type).
Example: A single column from a DataFrame.

DataFrame:

Two-dimensional data structure.
Heterogeneous data (each column can have a different type).
Example: A spreadsheet with labeled rows and columns.
```

#### Q.16 What are some common methods to summarize data in Pandas ? 
```bash
Use .describe() to get statistics like count, mean, std, min, max, etc.
Use .info() to understand the structure of the DataFrame.
Use .value_counts() to count occurrences of unique values in a Series.
```

#### Q.17 What are common file formats Pandas can read from or write to ? 
```bash
Reading:

CSV: pd.read_csv()
Excel: pd.read_excel()
SQL: pd.read_sql()
JSON: pd.read_json()

Writing:

CSV: .to_csv()
Excel: .to_excel()
```

#### Q.18 What is broadcasting in Pandas, and how is it used ? 
```bash
Broadcasting automatically aligns Series or DataFrame operations by index or column labels.

```

#### Q.19 How to make Label Encoding using Pandas ? 
```bash
Label encoding is used to convert categorical data into numerical data so that a machine-learning 
model can fit it.

pd.Categorical() converts the data into a Categorical type.
.codes gives the integer code for each category.

import pandas as pd

data = pd.Series(['Red', 'Blue', 'Green', 'Blue'])
encoded = pd.Categorical(data).codes
print(encoded)
```

#### Q.20  How to make Onehot Encoding using Pandas ? 
```bash
One-hot encoding is a technique for representing categorical data as numerical values in a 
machine-learning model.

import pandas as pd

df = pd.DataFrame({'Color': ['Red', 'Blue', 'Green']})

encoded = pd.get_dummies(df, columns=['Color'])
print(encoded)

o/p 
Color_Blue  Color_Green  Color_Red
0           0            0          1
1           1            0          0
2           0            1          0
```