```python
one_dimensional_arr = np.array([10, 12])
print(one_dimensional_arr) # [10 12]

b = np.arange(3)
print(b) # [0 1 2]

c = np.arange(1, 20, 3)
print(c) # [1 4 7 10 13 16]

lin_spaced_arr = np.linspace(0, 100, 5)
print(lin_spaced_arr) # [0. 25. 50. 75. 100. ]

lin_spaced_arr_int = np.linspace(0, 100, 5, dtype=int)
print(lin_spaced_arr_int) # [0 25 50 75 100 ]

c_int = np.arange(1, 20, 3, dtype=float)
print(c_int) # [1. 4. 7. 10. 13. 16. 19.]

char_arr = np.array(['Welcome to Math for ML!'])
print(char_arr) # ['Welcome to Math for ML!']
print(char_arr.dtype) # Prints the data type of the array
                      # <U23
                      # `U`: unicode string, `23`: 23-charachter

ones_arr = np.ones(3)
print(ones_arr) # [1. 1. 1.]

zeros_arr = np.zeros(3)
print(zeros_arr) # [0. 0. 0.]

empt_arr = np.empty(3)
print(empt_arr) # [0. 0. 0.]

rand_arr = np.random.rand(3)
print(rand_arr) # [0.1388916  0.80050128 0.6550602]
```

```python
two_dim_arr = np.array([[1,2,3], [4,5,6]])
print(two_dim_arr) # [[1 2 3]
                   #  [4 5 6]]

# 1-D array 
one_dim_arr = np.array([1, 2, 3, 4, 5, 6])

# Multidimensional array using reshape()
multi_dim_arr = np.reshape(
                    one_dim_arr, # the array to be reshaped
                    (2,3) # dimensions of the new array
                )
# Print the new 2-D array with two rows and three columns
print(multi_dim_arr) # [[1 2 3]
                     #  [4 5 6]]

# Dimension of the 2-D array multi_dim_arr
multi_dim_arr.ndim # 2

# Shape of the 2-D array multi_dim_arr
# Returns shape of 2 rows and 3 columns
multi_dim_arr.shape # (2, 3)

# Size of the array multi_dim_arr
# Returns total number of elements
multi_dim_arr.size # 6
```

```python
arr_1 = np.array([2, 4, 6])
arr_2 = np.array([1, 3, 5])

# Adding two 1-D arrays
addition = arr_1 + arr_2
print(addition) # [3 7 11]

# Subtracting two 1-D arrays
subtraction = arr_1 - arr_2
print(subtraction) # [1 1 1]

# Multiplying two 1-D arrays elementwise
multiplication = arr_1 * arr_2
print(multiplication) # [2 12 30]

vector = np.array([1, 2])
vector * 1.6 # [1.6, 3.2]
```

```python
# Select the third element of the array. Remember the counting starts from 0.
a = np.array([1, 2, 3, 4, 5])
print(a[2]) # 3

# Select the first element of the array.
print(a[0]) # 1

# Indexing on a 2-D array
two_dim = np.array(([1, 2, 3],
          [4, 5, 6], 
          [7, 8, 9]))

# Select element number 8 from the 2-D array using indices i, j and two sets of brackets
print(two_dim[2][1]) # 8

# Select element number 8 from the 2-D array, this time using i and j indexes in a single 
# set of brackets, separated by a comma
print(two_dim[2,1]) # 8

###########################################
a = np.array([1, 2, 3, 4, 5])

# Slice the array a to get the array [2,3,4]
sliced_arr = a[1:4]
print(sliced_arr) # [2 3 4]

# Slice the array a to get the array [1,2,3]
sliced_arr = a[:3]
print(sliced_arr) # [1 2 3]

# Slice the array a to get the array [3,4,5]
sliced_arr = a[2:]
print(sliced_arr)

# Slice the array a to get the array [1,3,5]
sliced_arr = a[::2]
print(sliced_arr)

# Note that a == a[:] == a[::]
print(f'a == a[:]: {a == a[:]}') # a == a[:]: [ True  True  True  True  True]
print(f'a[:] == a[::]: {a[:] == a[::]}') # a[:] == a[::]: [ True  True  True  True  True]

# Slice the two_dim array to get the first two rows
sliced_arr_1 = two_dim[0:2]
sliced_arr_1 # array([[1, 2, 3],
             #        [4, 5, 6]])

# Similarily, slice the two_dim array to get the last two rows
sliced_two_dim_rows = two_dim[1:3]
print(sliced_two_dim_rows) # [[4 5 6]
                           #  [7 8 9]]

# This example uses slice notation to get every row, and then pulls the second column.
# Notice how this example combines slice notation with the use of multiple indexes
sliced_two_dim_cols = two_dim[:,1]
print(sliced_two_dim_cols) # [2 5 8]
```

```python
a1 = np.array([[1,1], 
               [2,2]])
a2 = np.array([[3,3],
              [4,4]])
print(f'a1:\n{a1}') # a1:
                    # [[1 1]
                    #  [2 2]]
print(f'a2:\n{a2}') # a2:
                    # [[3 3]
                    #  [4 4]]

# Stack the arrays vertically
vert_stack = np.vstack((a1, a2))
print(vert_stack) # [[1 1]
                  #  [2 2]
                  #  [3 3]
                  #  [4 4]]

# Stack the arrays horizontally
horz_stack = np.hstack((a1, a2))
print(horz_stack) # [[1 1 3 3]
                  #  [2 2 4 4]]

# Split the horizontally stacked array into 2 separate arrays of equal size
horz_split_two = np.hsplit(horz_stack,2)
print(horz_split_two) # [array([[1, 1], [2, 2]]),
                      #  array([[3, 3], [4, 4]])]

# Split the horizontally stacked array into 4 separate arrays of equal size
horz_split_four = np.hsplit(horz_stack,4)
print(horz_split_four) # [array([[1], [2]]),
                       #  array([[1], [2]]),
                       #  array([[3], [4]]),
                       #  array([[3], [4]])]

# Split the horizontally stacked array after the first column
horz_split_first = np.hsplit(horz_stack,[1])
print(horz_split_first) # [array([[1], [2]]),
                        #  array([[1, 3, 3], [2, 4, 4]])]


# Split the vertically stacked array into 2 separate arrays of equal size
vert_split_two = np.vsplit(vert_stack,2)
print(vert_split_two)  # [array([[1, 1], [2, 2]]),
                       #  array([[3, 3], [4, 4]])]

# Split the vertically stacked array into 4 separate arrays of equal size
vert_split_four = np.vsplit(vert_stack,4)
print(vert_split_four) # [array([[1, 1]]), array([[2, 2]]), array([[3, 3]]), array([[4, 4]])]

# Split the vertically stacked array after the first and third row
vert_split_first_third = np.vsplit(vert_stack,[1,3])
print(vert_split_first_third)  # [array([[1, 1]]), array([[2, 2], [3, 3]]), array([[4, 4]])]

```