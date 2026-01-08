#### Q.1  What is the use of "flipud" function in NumPy ? 
```bash
The "flipud" function reverses the array elements row-wise or along axis = 1 and axis = 1 respectively.

Syntax: array object.flipud() or flipud(array)

array1 = [[10,20,30], [40, 50, 60], [70,80,90]]
np.flipud(array1)

ans : 
[[70 80 90]
 [40 50 60]
 [10 20 30]]
```

#### Q.2 Explain the concept of NumPy’s universal functions (ufuncs). ? 
```bash
Universal functions (ufuncs) are vectorized functions in NumPy that operate element-wise on arrays.
Work on NumPy arrays
Are fast (implemented in C)
Support broadcasting
Avoid explicit Python loops

result = arr * 2
np.add(a, 5)       # [6 7 8]
np.subtract(a, 1)  # [0 1 2]
np.multiply(a, 2)  # [2 4 6]
np.divide(a, 2)    # [0.5 1.  1.5]
np.sin(a)
np.cos(a)
np.tan(a)
```

#### Q.3 Discuss the purpose of the np.linspace() function in NumPy and provide an example.? 
```bash
np.linspace(start, stop, num) returns evenly spaced numbers over a specified range. It is 
often used to generate sequences for plotting.

import numpy as np
sequence = np.linspace(1, 10, 5) 
# Creates an array with 5 evenly spaced values from 1 to 10
```

#### Q.4 Explain the concept of memory layout in NumPy arrays. What is the significance of the order 
parameter in array creation functions like np.array() ?
```bash
Memory Layout: Refers to how elements are stored in the computer’s memory.
Order Parameter: Determines whether the array should be stored in row-major order 
(‘C’) or column-major order (‘F’).

import numpy as np
arr = np.array([[1, 2, 3], [4, 5, 6]], order=’F’)  # Column-major order
```

#### Q.5 Discuss the concept of NumPy’s broadcasting rules in detail. How does NumPy automatically align 
dimensions during operations ? 
```bash
Broadcasting Rules: Specify how NumPy handles element-wise operations on arrays with different shapes.
Automatic Alignment: NumPy compares dimensions element-wise, starting from the trailing dimensions. 
It automatically adds dimensions to the smaller array to match the larger one.

import numpy as np
A = np.array([[1, 2, 3], [4, 5, 6]])
B = np.array([10, 20, 30])
result = A + B  # Broadcasting the smaller array B to match the shape of A
```

#### Q.6  Imagine you are working on a project that involves handling a large dataset with missing values. 
How would you use NumPy to address and manage missing data efficiently ? 
```bash
In this scenario, use NumPy’s masked arrays, which can be created using the np.ma.masked_array() 
function. This allows you to represent missing or invalid values as masked elements, and perform 
operations on the data while ignoring these masked elements. Additionally, you can use functions 
like np.ma.masked_invalid() to automatically identify and mask invalid values in the dataset.
```

#### Q.7  You are tasked with optimizing the memory usage of a NumPy array that contains a large 
number of elements. What strategies would you employ to reduce the memory footprint while preserving 
data accuracy ? 
```bash
Choose the appropriate data type using the dtype parameter when creating the array to minimize 
memory consumption.
Utilize structured arrays if the data has multiple fields with different data types.
Explore the use of sparse matrices using scipy.sparse if the data has a significant number 
of zero values.
Use views or slices of arrays instead of creating unnecessary copies.
Consider breaking down large arrays into smaller chunks and processing them iteratively to 
avoid loading the entire dataset into memory at once.
```

#### Q.8 Your NumPy code is slow on large arrays. What do you do ? 
```bash
Avoid Python loops
Use vectorized operations
Use broadcasting
Avoid unnecessary array copies
```

#### Q.9 Creating a huge array raises MemoryError. How do you handle it ? 
```bash
Use smaller dtypes (int32, float32)
Use memory-mapped arrays
Process data in chunks

np.memmap("data.dat", dtype="float32", mode="w+", shape=(10000, 10000))
```

#### Q.10 You get a broadcasting error. Why ? 
```bash
Shapes are incompatible
Broadcasting rules violated
```

#### Q.11 Why does modifying one array affect another ?
```bash
They share the same memory (view vs copy)
b = a.view()   # shares memory
c = a.copy()   # independent
```

#### Q.12 How do you apply operations row-wise or column-wise ? 
```bash
Use axis parameter
Prefer vectorized reductions

arr.sum(axis=1)  # rows
arr.sum(axis=0)  # columns
```

#### Q.13 How do you get unique values quickly ? 
```bash
np.unique
np.unique(arr)
```

#### Q.14 How do you filter values > 10 ? 
```bash
Use boolean masking.
arr[arr > 10]
```

#### Q.15 Replace negatives with 0. ? 
```bash
np.where
np.where(arr < 0, 0, arr)
```

#### Q.16 Sort rows based on second column. ? 
```bash
arr[arr[:, 1].argsort()]
```

#### Q.17 Why does a == b fail ? 
```bash
Floating-point precision issue
np.isclose(a, b)
```

#### Q.18 Storing strings consumes too much memory ? 
```bash
Use categorical encoding
Map strings to integers
np.unique(arr, return_inverse=True)
```

#### Q.19 When prefer NumPy over Pandas ? 
```bash
Heavy numerical computation
Large homogeneous data
No need for labels or indices
```

#### Q.20 How do you check array shape and size ? 
```bash
arr.shape
arr.size
arr.ndim
```