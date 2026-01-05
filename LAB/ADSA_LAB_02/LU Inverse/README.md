# 🔢 Matrix Inversion Using LU Decomposition (C)

This project implements **matrix inversion using LU Decomposition** in the **C programming language**.  
The algorithm decomposes a given square matrix **A** into:

`A = L × U`  

where:
- **L** is a *lower triangular matrix* with diagonal elements = 1
- **U** is an *upper triangular matrix*

Once the decomposition is complete, the inverse of **A** is computed by solving:

`A X = I`  

column by column using **forward and backward substitution**.

---

## 📌 Key Concepts Used

- LU Decomposition (Doolittle’s method)
- Forward Substitution (solving L·Y = B)
- Backward Substitution (solving U·X = Y)
- Matrix inversion via solving multiple linear systems

---

## ⚙️ How the Program Works  
### **1️⃣ LU Decomposition**
The input matrix `A` is decomposed into: A = L × U  

- `L` → Lower triangular matrix with diagonal = 1  
- `U` → Upper triangular matrix  

If any pivot element becomes zero, the matrix is declared **singular** and inversion stops.

---

### **2️⃣ Solve AX = I**
To compute the inverse:

- Each column of the identity matrix `I` is treated as a RHS vector.
- Solve:

L·Y = eᵢ (Forward Substitution)
U·X = Y (Backward Substitution)  

- The solution vector `X` forms one column of `A⁻¹`.

This process is repeated for all columns.

---

# Time Complexity
Let n be the order of the matrix.

1️⃣ LU Decomposition
- Nested loops over matrix  
O(n³)  

2️⃣ Forward Substitution
- For each column of identity matrix  
O(n²) × n = O(n³)  

3️⃣ Backward Substitution  
O(n²) × n = O(n³)  

✅ Overall Time Complexity: `O(n³)`

---

# Space Complexity
Storage Used:
- Matrix A → O(n²)
- Matrices L and U → O(n²)
- Inverse matrix → O(n²)
- Temporary vectors → O(n)

✅ Overall Space Complexity: `O(n²)`  

---

### **Sample Input**
Enter order of matrix: 3  
Enter matrix elements:  
2 1 1  
1 3 2  
1 0 0  


### **Sample Output**
The final inverse matrix is printed in matrix form.  

Inverse Matrix:  
 0.0000  0.0000  1.0000  
-2.0000  1.0000  3.0000  
 3.0000 -1.0000 -5.0000  
