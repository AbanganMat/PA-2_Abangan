# NumPy Exercises: Normalization & Divisible by 3 Problems from Abangan

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
```
\[
Z = \frac{X - \bar{X}}{\sigma}
\]
```
#### Code:
```python
import numpy as np  # Import the NumPy library for numerical operations

# Create a 5x5 array (matrix) filled with random values between 0 and 1
X = np.random.rand(5, 5)

# Calculate the mean (average) of all elements in the array
mean_X = X.mean()

# Calculate the standard deviation (how spread out the values are)
std_X = X.std()

# Check if standard deviation is zero to avoid division by zero errors
if std_X == 0:
    print("Standard deviation is zero, normalization cannot be performed.")
else:
    # Normalize the array: (value - mean) / standard deviation
    X_normalized = (X - mean_X) / std_X

    # Save the normalized array to a .npy file
    np.save('X_normalized.npy', X_normalized)

    # Display the original array
    print("Original Array:\n", X)

    # Display the normalized array
    print("\nNormalized Array:\n", X_normalized)

    # Load the saved normalized array from the .npy file
    loaded_X_normalized = np.load('X_normalized.npy')

    # Show the loaded array to confirm it was saved and loaded correctly
    print("\nLoaded Normalized Array from File:\n", loaded_X_normalized)
```
<img width="565" height="368" alt="Screenshot 2025-10-06 at 08 28 38" src="https://github.com/user-attachments/assets/9bde6bc6-a29e-4d1f-a995-4a243c952b7b" />

### 2. Divisble by 3
```
import numpy as np  # Import the NumPy library for numerical operations

# Create an array of integers from 1 to 100
# Then square each number to get their squares
A = np.arange(1, 101)**2

# Reshape the 1D array into a 10x10 (2D) array
A = A.reshape((10, 10))

# Display the 10x10 array of squares
print("10x10 Array of Squares of the First 100 Positive Integers:\n", A)

# Find elements that are divisible by 3 using the modulo (%) operator
# The condition (A % 3 == 0) returns True for elements divisible by 3
div_by_3 = A[A % 3 == 0]

# Display only the elements divisible by 3
print("\nElements Divisible by 3:\n", div_by_3)

# Save the elements divisible by 3 into a .npy file
np.save('div_by_3.npy', div_by_3)

# Load the saved array from the .npy file
loaded_div_by_3 = np.load('div_by_3.npy')

# Display the loaded array to verify it was saved and loaded correctly
print("\nLoaded Elements Divisible by 3 from File:\n", loaded_div_by_3)

```
<img width="510" height="353" alt="Screenshot 2025-10-06 at 08 28 27" src="https://github.com/user-attachments/assets/ad579fea-d6ab-4380-a206-f07137217647" />
