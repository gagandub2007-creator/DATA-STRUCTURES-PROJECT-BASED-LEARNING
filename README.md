# Sparse Matrix Storage Tool

A simple C++ tool that stores a sparse matrix in **CSR (Compressed Sparse Row)** format, compares its storage with a dense matrix, and computes the matrix-vector product **y = A × x**.

This project is part of the Data Structures Lab (B.Tech CSE, 3rd Semester).

## Features

- Reads a matrix and a vector from the user
- Converts the dense matrix into CSR format (values, column indices, row pointers)
- Shows the storage comparison between dense and CSR formats
- Computes the sparse matrix-vector multiplication using CSR

## Requirements

- A C++ compiler with C++11 support (for example `g++`)

## Build and Run

```bash
g++ -std=c++11 -o sparse sparse.cpp
./sparse
```

## Example

Input (4 × 4 matrix and vector `1 2 3 4`):

```
Enter number of rows: 4
Enter number of columns: 4
5 0 0 1
0 0 3 0
0 0 0 0
2 0 0 7
1 2 3 4
```

Output:

```
Dense storage: 16 values
CSR storage:   5 values + 5 column indices + 5 row pointers

Result y = A * x:
y[0] = 9
y[1] = 9
y[2] = 0
y[3] = 30
```

## How CSR Works

For a matrix, CSR keeps three arrays:

| Array       | Contents                                   |
|-------------|--------------------------------------------|
| `val`       | Nonzero values, row by row                 |
| `colIndex`  | Column number of each nonzero value        |
| `rowPtr`    | Index in `val` where each row starts       |

Only nonzero values are stored, so memory use is small when most entries are zero.

## Project Structure

```
.
├── sparse.cpp   # Source code
└── README.md    # This file
```

## Author

- **Name:** Gagan Dubey
- **Enrollment Number:** 26118002725
- **Subject:** Data Structures Lab
- **Faculty:** Dr. Akash Bhardwaj

## License

This project is for academic use.
