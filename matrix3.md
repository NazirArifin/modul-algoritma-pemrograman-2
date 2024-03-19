Modul 9 - Operasi Matrix (Invers, Transpose, Adjoin, Kofaktor)

## Tujuan Pembelajaran

1. Siswa memahami konsep operasi invers matrix
2. Siswa mampu melakukan operasi invers matrix
3. Siswa memahami konsep operasi transpose matrix
4. Siswa mampu melakukan operasi transpose matrix
5. Siswa memahami konsep operasi adjoin matrix
6. Siswa mampu melakukan operasi adjoin matrix
7. Siswa memahami konsep operasi kofaktor matrix
8. Siswa mampu melakukan operasi kofaktor matrix

## Materi

### Konsep Operasi Invers Matrix

Operasi invers matrix adalah operasi yang dilakukan pada sebuah matrix. Operasi ini dilakukan dengan cara mencari matrix yang apabila dikalikan dengan matrix asal akan menghasilkan matrix identitas. Operasi ini hanya dapat dilakukan pada matrix yang memiliki determinan yang tidak sama dengan 0. 

Operasi invers matrix dapat diilustrasikan sebagai berikut:

```plaintext
A = | 1 2 |   A^-1 = | -2  1 |
    | 3 4 |          |  1 -1 |
```

Pada contoh di atas, matrix A memiliki ukuran 2x2. Operasi invers matrix A dilakukan dengan cara mencari matrix A^-1 yang apabila dikalikan dengan matrix A akan menghasilkan matrix identitas.

> Matrix Identitas adalah matrix yang memiliki nilai 1 pada diagonal utama dan nilai 0 pada seluruh elemen lainnya.

### Algoritma Invers Matrix

Algoritma invers matrix dapat diilustrasikan sebagai berikut:

```python
def determinant(matrix):
    if len(matrix) == 1:
        return matrix[0][0]
    elif len(matrix) == 2:
        return matrix[0][0] * matrix[1][1] - matrix[0][1] * matrix[1][0]
    else:
        det = 0
        for i in range(len(matrix)):
            minor = [row[:i] + row[i+1:] for row in (matrix[1:])]
            det += ((-1) ** i) * matrix[0][i] * determinant(minor)
        return det

def inverse_matrix(matrix):
    det = determinant(matrix)
    if det == 0:
        return "Matrix tidak memiliki invers"
    else:
        cofactors = []
        for i in range(len(matrix)):
            row = []
            for j in range(len(matrix)):
                minor = [row[:j] + row[j+1:] for row in (matrix[:i] + matrix[i+1:])]
                row.append(((-1) ** (i+j)) * determinant(minor))
            cofactors.append(row)
        adjoint = list(map(list, zip(*cofactors)))
        inverse = [[element / det for element in row] for row in adjoint]
        return inverse
```

Pada contoh di atas, matrix adalah matrix yang akan diinvers. Algoritma ini akan melakukan iterasi sebanyak n kali, dimana n adalah panjang dari matrix. Pada setiap iterasi, algoritma akan menghitung determinan dari matrix, lalu mencari kofaktor dan adjoin dari matrix, dan terakhir menghitung invers dari matrix. 

Untuk melakukan operasi invers matrix, kita dapat menggunakan fungsi inverse_matrix seperti pada contoh di bawah ini.

```python
A = [
    [1, 2],
    [3, 4]
]

A_inverse = inverse_matrix(A)
print(A_inverse) # [[-2.0, 1.0], [1.5, -0.5]]
```

### Konsep Operasi Transpose Matrix

Operasi transpose matrix adalah operasi yang dilakukan pada sebuah matrix. Operasi ini dilakukan dengan cara menukar baris dan kolom pada matrix. 

Operasi transpose matrix dapat diilustrasikan sebagai berikut:

```plaintext
A = | 1 2 |   A^T = | 1 3 |
    | 3 4 |         | 2 4 |
```

Pada contoh di atas, matrix A memiliki ukuran 2x2. Operasi transpose matrix A dilakukan dengan cara menukar baris dan kolom pada matrix A. 

### Algoritma Transpose Matrix

Algoritma transpose matrix dapat diilustrasikan sebagai berikut:

```python
def transpose_matrix(matrix):
    return [[matrix[j][i] for j in range(len(matrix))] for i in range(len(matrix[0]))]
```

Pada contoh di atas, matrix adalah matrix yang akan diinvers. Algoritma ini akan melakukan iterasi sebanyak m kali, dimana m adalah panjang dari matrix. Pada setiap iterasi, algoritma akan menukar baris dan kolom pada matrix.

Untuk melakukan operasi transpose matrix, kita dapat menggunakan fungsi transpose_matrix seperti pada contoh di bawah ini.

```python
A = [
    [1, 2],
    [3, 4],
    [5, 6]
]

A_transpose = transpose_matrix(A)
print(A_transpose) # [[1, 3, 5], [2, 4, 6]]
```

### Konsep Operasi Adjoin Matrix

Operasi adjoin matrix adalah operasi yang dilakukan pada sebuah matrix. Operasi ini dilakukan dengan cara mengubah elemen-elemen matrix dengan cara mengubah tanda dari elemen-elemen tersebut. 

Operasi adjoin matrix dapat diilustrasikan sebagai berikut:

```plaintext
A = | 1 2 |   adj(A) = |  1 -2 |
    | 3 4 |            | -3  4 |
```

Pada contoh di atas, matrix A memiliki ukuran 2x2. Operasi adjoin matrix A dilakukan dengan cara mengubah tanda dari elemen-elemen matrix A. 

### Algoritma Adjoin Matrix

Algoritma adjoin matrix dapat diilustrasikan sebagai berikut:

```python
def adjoin_matrix(matrix):
    return [[(-1) ** (i+j) * determinant([row[:j] + row[j+1:] for row in (matrix[:i] + matrix[i+1:])]) for j in range(len(matrix))] for i in range(len(matrix))]
```

Pada contoh di atas, matrix adalah matrix yang akan diinvers. Algoritma ini akan melakukan iterasi sebanyak n kali, dimana n adalah panjang dari matrix. Pada setiap iterasi, algoritma akan menghitung determinan dari matrix, lalu mengubah tanda dari elemen-elemen matrix.

Untuk melakukan operasi adjoin matrix, kita dapat menggunakan fungsi adjoin_matrix seperti pada contoh di bawah ini.

```python
A = [
    [1, 2],
    [3, 4]
]

A_adjoin = adjoin_matrix(A)
print(A_adjoin) # [[1, -2], [-3, 4]]
```

### Konsep Operasi Kofaktor Matrix

Operasi kofaktor matrix adalah operasi yang dilakukan pada sebuah matrix. Operasi ini dilakukan dengan cara mengubah tanda dari elemen-elemen matrix dan menghitung determinan dari matrix. 

Operasi kofaktor matrix dapat diilustrasikan sebagai berikut:

```plaintext
A = | 1 2 |   cofactor(A) = |  1 -2 |
    | 3 4 |                 | -3  4 |
```

Pada contoh di atas, matrix A memiliki ukuran 2x2. Operasi kofaktor matrix A dilakukan dengan cara mengubah tanda dari elemen-elemen matrix A dan menghitung determinan dari matrix.

### Algoritma Kofaktor Matrix

Algoritma kofaktor matrix dapat diilustrasikan sebagai berikut:

```python
def kofactor_matrix(matrix):
    return [[(-1) ** (i+j) * determinant([row[:j] + row[j+1:] for row in (matrix[:i] + matrix[i+1:])]) for j in range(len(matrix))] for i in range(len(matrix))]
```

Pada contoh di atas, matrix adalah matrix yang akan diinvers. Algoritma ini akan melakukan iterasi sebanyak n kali, dimana n adalah panjang dari matrix. Pada setiap iterasi, algoritma akan menghitung determinan dari matrix, lalu mengubah tanda dari elemen-elemen matrix.

Untuk melakukan operasi kofaktor matrix, kita dapat menggunakan fungsi kofactor_matrix seperti pada contoh di bawah ini.

```python
A = [
    [1, 2],
    [3, 4]
]

A_kofactor = kofactor_matrix(A)
print(A_kofactor) # [[1, -2], [-3, 4]]
```

## Tugas

1. Buatlah sebuah program yang dapat melakukan operasi invers matrix.
2. Buatlah sebuah program yang dapat melakukan operasi transpose matrix.
3. Buatlah sebuah program yang dapat melakukan operasi adjoin matrix.
4. Buatlah sebuah program yang dapat melakukan operasi kofaktor matrix.




