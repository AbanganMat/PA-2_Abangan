# NumPy Exercises: Normalization & Divisible by 3 Problems

This repository contains two Python exercises demonstrating basic **NumPy** operations such as array creation, normalization, reshaping, element selection, and saving/loading `.npy` files.  

---

##  I. Intended Learning Outcomes
1. To identify the codes and functions incorporated in the NumPy library.  
2. To be able to apply and use the different codes and functions in creating a Python program using the NumPy library.  

---

##  II. Instructions
Write a Python script/code in **Jupyter Notebook** to solve the given problems.  
You may submit your Jupyter notebook in the dedicated submission bin.  

---

##  III. Coding Exercises

###  1. Normalization Problem
Normalization is one of the most basic preprocessing techniques in data analytics.  
It involves **centering** (subtracting the mean) and **scaling** (dividing by the standard deviation):  

\[
Z = \frac{X - \bar{X}}{\sigma}
\]

#### Code:
```python
import numpy as np

# Create 5x5 ndarray with random values
X = np.random.rand(5, 5)

# Calculate mean and standard deviation
mean_X = X.mean()
std_X = X.std()

# Check for standard deviation to avoid division by zero
if std_X == 0:
    print("Standard deviation is zero, normalization cannot be performed.")
else:
    # Normalize array
    X_normalized = (X - mean_X) / std_X

    # Save normalized array to a .npy file
    np.save('X_normalized.npy', X_normalized)

    # Output: Original and Normalized Array
    print("Original Array:\n", X)
    print("\nNormalized Array:\n", X_normalized)

    # Load and verify the saved normalized array
    loaded_X_normalized = np.load('X_normalized.npy')
    print("\nLoaded Normalized Array from File:\n", loaded_X_normalized)


### 2. Divisble by 3

import numpy as np  

# Create 10x10 ndarray of squares of integers from 1 to 100
A = np.arange(1, 101)**2
A = A.reshape((10, 10))  # Reshape into a 10x10 array

# Output: 10x10 array
print("10x10 Array of Squares of the First 100 Positive Integers:\n", A)

# Determine elements divisible by 3 using modulo operation
div_by_3 = A[A % 3 == 0]

# Output: Elements divisible by 3
print("\nElements Divisible by 3:\n", div_by_3)

# Save results to a .npy file
np.save('div_by_3.npy', div_by_3)

# Load and verify the saved array
loaded_div_by_3 = np.load('div_by_3.npy')
print("\nLoaded Elements Divisible by 3 from File:\n", loaded_div_by_3)
