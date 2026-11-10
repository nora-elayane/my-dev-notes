# Matrix Transpose

> **Category:** Matrix Operations  
> **Difficulty:** Beginner – Intermediate  
> **Time Complexity:** O(m × n)  
> **Space Complexity:** O(m × n) — Using a new matrix

## 1. Definition

The **Transpose of a Matrix** is an operation that exchanges the rows and columns of a matrix.

- Rows become columns.
- Columns become rows.
- Elements keep their values, but their positions change.

The transpose of matrix `A` is written as `Aᵀ`.

**Example:**

Original matrix:

```text
A =  1  2  3
     4  5  6
```

Transposed matrix:

```text
Aᵀ = 1  4
     2  5
     3  6
```

## 2. How It Works

Each element changes its position by exchanging its row and column indices.

**Mathematical rule:**

\[
A^T[j][i] = A[i][j]
\]

Where:
- `i` represents the original row.
- `j` represents the original column.

**Example:**

```text
Original: A[0][1] = 2

After transpose:

Aᵀ[1][0] = 2
```

The value stays the same, but its position changes.

## 3. Matrix Dimensions

If the original matrix has `m` rows and `n` columns, the transposed matrix has `n` rows and `m` columns.

| Original Matrix | Transposed Matrix |
|---|---|
| 2 × 3 | 3 × 2 |
| 3 × 4 | 4 × 3 |
| 4 × 2 | 2 × 4 |
| 3 × 3 | 3 × 3 |

**Important:** Rows and columns exchange their dimensions.

## 4. Step-by-Step Example

Consider this matrix:

```java
int[][] matrix = {
    {10, 20, 30},
    {40, 50, 60}
};
```

Original matrix:

```text
10  20  30
40  50  60
```

After transpose:

```text
10  40
20  50
30  60
```

### Element Position Changes

| Original Position | Value | New Position |
|---|---:|---|
| [0][0] | 10 | [0][0] |
| [0][1] | 20 | [1][0] |
| [0][2] | 30 | [2][0] |
| [1][0] | 40 | [0][1] |
| [1][1] | 50 | [1][1] |
| [1][2] | 60 | [2][1] |

## 5. Java Implementation

To transpose a matrix, we create a new matrix with reversed dimensions.

```java
public class MatrixTranspose {

    public static void main(String[] args) {

        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6}
        };

        int rows = matrix.length;
        int cols = matrix[0].length;

        // Create a new matrix with reversed dimensions
        int[][] transpose = new int[cols][rows];

        // Transpose the matrix
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {

                transpose[j][i] = matrix[i][j];

            }
        }

        // Display the result
        for (int i = 0; i < transpose.length; i++) {
            for (int j = 0; j < transpose[i].length; j++) {

                System.out.print(transpose[i][j] + " ");

            }
            System.out.println();
        }
    }
}
```

**Output:**

```text
1 4
2 5
3 6
```

## 6. Understanding the Important Code

### A. Get Matrix Dimensions

```java
int rows = matrix.length;
int cols = matrix[0].length;
```

- `matrix.length`: Number of rows.
- `matrix[0].length`: Number of columns (for a non-empty rectangular matrix).

### B. Create the Transposed Matrix

```java
int[][] transpose = new int[cols][rows];
```

We exchange the dimensions because rows become columns and columns become rows.

### C. Exchange Element Positions

```java
transpose[j][i] = matrix[i][j];
```

This is the main instruction of the transpose operation.

It copies each element from its original position to its new position.

## 7. In-Place Transposition

For a **square matrix** (same number of rows and columns), we can transpose the matrix without creating another matrix.

We exchange elements on opposite sides of the main diagonal.

**Example:**

Before:

```text
1  2  3
4  5  6
7  8  9
```

After:

```text
1  4  7
2  5  8
3  6  9
```

### Java Implementation

```java
for (int i = 0; i < matrix.length; i++) {

    for (int j = i + 1; j < matrix.length; j++) {

        int temp = matrix[i][j];

        matrix[i][j] = matrix[j][i];

        matrix[j][i] = temp;
    }
}
```

**How does it work?**

- `temp` temporarily stores an element.
- The two opposite elements exchange their values.
- `j = i + 1` avoids exchanging the diagonal elements and repeating previous exchanges.

**Important:** This method works for square matrices, not rectangular matrices.

## 8. Time and Space Complexity

Let:
- `m` = Number of rows.
- `n` = Number of columns.

| Operation | Complexity |
|---|---|
| Time Complexity | O(m × n) |
| Space Complexity (new matrix) | O(m × n) |
| Space Complexity (in-place square matrix) | O(1) extra space |

Every element is visited once when creating a new transposed matrix.

## 9. Important Notes

- Transpose exchanges rows and columns.
- The notation is `Aᵀ`.
- The original matrix dimensions `m × n` become `n × m`.
- The element at `[i][j]` moves to `[j][i]`.
- A new matrix is generally used for rectangular matrices.
- In-place transposition is possible for square matrices.
- The main diagonal elements do not change position.

## 10. Practice Exercises

**Exercise 1 — Basic Transpose**

Transpose the following matrix:

```java
int[][] matrix = {
    {1, 2},
    {3, 4},
    {5, 6}
};
```

**Exercise 2 — Dimensions**

Create a Java program that displays the dimensions of a matrix before and after transposition.

**Exercise 3 — Method**

Create a method called `transposeMatrix()` that receives a matrix and returns its transpose.

**Exercise 4 — In-Place Transpose**

Transpose a 3 × 3 matrix without creating another matrix.

**Exercise 5 — Reasoning**

Explain why the in-place transposition method cannot be directly applied to a rectangular matrix.

---

## 11. Key Takeaways

- Matrix Transpose exchanges rows and columns.
- Each element changes position from `[i][j]` to `[j][i]`.
- Matrix dimensions are reversed.
- Nested loops are used to visit all elements.
- A new matrix is used for general rectangular matrices.
- Square matrices can be transposed in-place.
- Time complexity is O(m × n).
