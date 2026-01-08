#### Q.1 What is NumPy and how to create a NumPy array ? 
```bash
NumPy is used for numerical and scientific computing. It offers support for arrays, matrices 
and a variety of mathematical operations that can effectively operate on these arrays.
Using np. array()
np.zeros()
np.ones()
np.full()
np.arange()
np.linspace()
```

#### Q.2 How do you calculate the dot product of two NumPy arrays ? 
```bash
numpy.dot(a, b)
a @ b
```

#### Q.3 How do you reshape a NumPy array ? 
```bash
array1= original_array.reshape(new_shape)
array1 = np.reshape(original_array, new_shape)
```

#### Q.4 How to perform element-wise operations on NumPy arrays ? 
```bash
import numpy as np

# Create two NumPy arrays
array1 = np.array([1, 2, 3, 4, 5])
array2 = np.array([6, 7, 8, 9, 10])

# Perform element-wise operations
result_addition = array1 + array2
result_subtract = array1 - array2
result_multiply = array1 * array2
result_divide = array1 / array2
result_power = np.power(array1, 2)
```

#### Q.5 How to generate random numbers with NumPy ? 
```bash
random_float = np.random.rand()
random_integer = np.random.randint()
random_float = np.random.randn()
```

#### Q.6 How can you access elements in a NumPy array based on specific conditions ? 
```bash
import numpy as np
arr = np.array([1, 2, 3, 4, 5])
condition = arr > 3
selected_elements = arr[condition]
```

#### Q.7 What are some common data types supported by NumPy ? 
```bash
int
float
complex
bool
object
datetime
```

#### Q.8 How can you concatenate two NumPy arrays vertically ? 
```bash
array= np.vstack((array1, array2))
array= np.concatenate((array1, array2), axis=0)
```

#### Q.9 What is Matrix Inversion in NumPy ? 
```bash
Matrix inversion in NumPy refers to the process of finding the inverse of a square matrix. 
The identity matrix is produced when multiplying the original matrix by the inverse of the 
matrix. In other words, if A is a square matrix and A^(-1) is its inverse, then A * A^(-1) = I, 
where I is the identity matrix.

import numpy as np
A = np.array([[1, 2, 3],
              [0, 1, 4],
              [5, 6, 0]])

A_inverse = np.linalg.inv(A)
```

#### Q.10 Convert a multidimensional array to 1D array ? 
```bash
multidimensional_array = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
one_dimensional_array = multidimensional_array.flatten()
or 
one_dimensional_array = multidimensional_array.ravel()
print("one dimensional array", one_dimensional_array)

o/p
one dimensional array [1 2 3 4 5 6 7 8 9]
```

#### Q.11  How can you identify outliers in a NumPy array ? 
```bash
Calculate Descriptive Statistics
mean = np.mean(arr)
std = np.std(arr)

Using IQR: IQR (Interquartile Range) 
Using IQR: IQR (Interquartile Range) is the difference between the 75th percentile 
(Q3) and the 25th percentile (Q1), representing the spread of the middle 50% of the data.

import numpy as np

arr = np.array([10, 12, 12, 13, 12, 11, 300, 14, 13, 12])

# Calculate Q1 (25th percentile) and Q3 (75th percentile)
Q1 = np.percentile(arr, 25)
Q3 = np.percentile(arr, 75)
IQR = Q3 - Q1

# Define bounds
lower_bound = Q1 - 1.5 * IQR
upper_bound = Q3 + 1.5 * IQR

# Identify outliers
outliers = arr[(arr < lower_bound) | (arr > upper_bound)]

print("Outliers:", outliers)
```

#### Q.12 Why NumPy is faster than list ? 
```bash
Homogeneous Data
Contiguous Memory Allocation
Vectorization
Low-Level Optimizations
```

#### Q.13 How can you find the unique elements in an array in NumPy ? 
```bash
import numpy as np 
array = np.array([1, 2, 3, 1, 2, 3, 3, 4, 5, 6, 7, 5]) 
unique = np.unique(array) 
print(unique)
```

#### Q.14 How do you check the shape and size of a NumPy array ? 
```bash
import numpy as np

arr = np.array([[1, 2, 3], [4, 5, 6]])
print(arr.shape)  # Output: (2, 3)
print(arr.size)   # Output: 6
```

#### Q.15 Is there a way to quickly and easily apply functions to each row and column of a 2D array ? 
```bash
import numpy as np
arr = np.array([[1, 2, 3],
                [4, 5, 6]])
row_sum = np.apply_along_axis(np.sum, axis=1, arr=arr)
print(row_sum)
```

#### Q.16 How do you normalize data using NumPy ? 
```bash
import numpy as np

data = np.array([10, 20, 30, 40, 50])
normalized = (data - np.min(data)) / (np.max(data) - np.min(data))
print(normalized)
```

#### Q.17 How do you compute the correlation coefficient between two datasets ? 
```bash
The correlation coefficient measures how strongly two datasets (variables) are 
related and in what direction.
“When one variable changes, how does the other change?”
+1	Perfect positive correlation
0	No correlation
-1	Perfect negative correlation

import numpy as np

x = np.array([1, 2, 3, 4, 5])
y = np.array([2, 4, 6, 8, 10])
correlation = np.corrcoef(x, y)
print(correlation)
```

#### Q.18 How will you find the nearest value in a given numpy array ? 
```bash
import numpy as np
def find_nearest_value(arr, value):
   arr = np.asarray(arr)
   idx = (np.abs(arr - value)).argmin()
   return arr[idx]
#Driver code
arr = np.array([ 0.21169,  0.61391, 0.6341, 0.0131, 0.16541,  0.5645,  0.5742])
value = 0.52
print(find_nearest_value(arr, value))
```

#### Q.19 Print an array range between 1 to 35 and show 7 integer random numbers ? 
```bash
rand_arr = np.random.randint(1,35,7)
rand_arr
```

#### Q.20 How do you count the frequency of a given positive value appearing in the NumPy array ? 
```bash
arr = np.array([1, 2, 1, 3, 5, 0, 0, 0, 2, 3])
result = np.bincount(arr)

ans : [3 2 2 2 0 1]
```