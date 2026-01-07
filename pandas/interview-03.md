#### Q.1 Your Pandas code works but is very slow on large datasets. What do you do ? 
```bash
Avoid loops (iterrows, itertuples)
Use vectorized operations
Use apply() only if necessary
Filter data early
```

#### Q.2 A CSV file is too large and crashes memory. How do you handle it ? 
```bash
Use chunksize
Process data in batches

for chunk in pd.read_csv("big.csv", chunksize=100000):
    process(chunk)
```

#### Q.3 NaN values appear after merge. Why ? 
```bash
Join keys don’t match
Different data types
Missing values in one dataset
```

#### Q.4 Numeric operations fail because column is object. Fix ? 
```bash
Convert dtype explicitly
df["price"] = pd.to_numeric(df["price"], errors="coerce")
```

#### Q.5 You see duplicate records. How do you fix? 
```bash
Identify duplicates
Drop them properly
df.drop_duplicates(subset=["id"], keep="first", inplace=True)
```

#### Q.6 Filtering by date doesn’t work. Why ? 
```bash
Column is string, not datetime
df["date"] = pd.to_datetime(df["date"])
df[df["date"] > "2024-01-01"]
```

#### Q.7 After merge, row count explodes. Why ? 
```bash
Many-to-many join
Duplicate keys on both sides
df1["id"].is_unique
```

#### Q.8 Pandas DataFrame uses too much memory. How to optimize ? 
```bash
Downcast data types
Use category for strings
df["type"] = df["type"].astype("category")
```

#### Q.9 You get SettingWithCopyWarning. Why ? 
```bash
Modifying a view instead of copy
df.loc[df["age"] > 30, "group"] = "Senior"
```

#### Q.10 GroupBy results look wrong. What could be wrong?
```bash
Aggregating wrong column
Missing reset_index()
df.groupby("dept")["salary"].mean().reset_index()
```

#### Q.11 apply(axis=1) is slow. Fix ? 
```bash
Use vectorized logic
df["total"] = df["a"] + df["b"]
```

#### Q.12 Rename didn’t change column names. Why ? 
```bash
Forgot inplace=True or reassignment
df = df.rename(columns={"old": "new"})
```

#### Q.13 Excel file reading is slow. How to improve ? 
```bash
Read only required columns
Convert to CSV/Parquet
pd.read_excel("file.xlsx", usecols=["A", "B"])
```

#### Q.14 How do you handle missing data ? 
```bash
Drop or fill depending on context
df.fillna(0)
df.dropna(subset=["salary"])
```

#### Q.15 Sorting gives wrong order. Why ? 
```bash
Column is string, not numeric
df["score"] = df["score"].astype(int)
df.sort_values("score")
```

#### Q.16 Filtering doesn’t work as expected ? 
```bash
Missing parentheses
df[(df["age"] > 25) & (df["salary"] > 50000)]
```

#### Q.17 Index causes issues after operations ? 
```bash
Reset index
df.reset_index(drop=True, inplace=True)
```

#### Q.18 Pandas and SQL results differ. Why ? 
```bash
NULL handling differences
Join logic mismatch
df.isna().sum()
```

#### Q.19 CSV output has index column unexpectedly. ? 
```bash
Forgot index=False
df.to_csv("output.csv", index=False)
```

#### Q.20 When should you prefer NumPy over Pandas ? 
```bash
Heavy numerical computation
No need for labels/index
```