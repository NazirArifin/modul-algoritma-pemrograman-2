Modul 8 - Operasi Matrix (Perkalian dan Determinan)

## Tujuan Pembelajaran

1. Siswa memahami konsep operasi perkalian matrix
2. Siswa mampu melakukan operasi perkalian matrix
3. Siswa memahami konsep determinan matrix
4. Siswa mampu melakukan operasi mencari determinan matrix

## Materi

### Konsep Operasi Perkalian Matrix

Operasi perkalian matrix adalah operasi yang dilakukan pada dua buah matrix. Operasi ini dilakukan dengan cara mengalikan elemen-elemen yang berada pada baris dan kolom yang sama pada matrix pertama, lalu menjumlahkan hasil perkalian tersebut. Operasi ini hanya dapat dilakukan pada matrix yang sesuai, yaitu matrix A berordo m x n dan matrix B berordo n x p. Hasil perkalian dari kedua matrix ini adalah matrix C yang berordo m x p. 

Operasi perkalian matrix dapat diilustrasikan sebagai berikut:

```plaintext
A = | 1 2 |   B = | 3 4 |   A x B = | 1*3+2*5 1*4+2*6 |
    | 5 6 |       | 5 6 |           | 5*3+6*5 5*4+6*6 |
```

Pada contoh di atas, matrix A memiliki ukuran 2x2 dan matrix B memiliki ukuran 2x2. Operasi perkalian matrix A dan B dilakukan dengan cara mengalikan elemen-elemen yang berada pada baris dan kolom yang sama pada matrix A, lalu menjumlahkan hasil perkalian tersebut. Sehingga, hasil perkalian matrix A dan B adalah matrix C yang memiliki elemen-elemen yang merupakan hasil perkalian elemen-elemen matrix A dan B.

### Algoritma Perkalian Matrix

Algoritma perkalian matrix dapat diilustrasikan sebagai berikut:

```python
def multiply_matrix(A, B):
    C = []
    for i in range(len(A)):
        row = []
        for j in range(len(B[0])):
            total = 0
            for k in range(len(B)):
                total += A[i][k] * B[k][j]
            row.append(total)
        C.append(row)
    return C
```

Pada contoh di atas, A dan B adalah dua buah matrix yang akan dikalikan. Algoritma ini akan melakukan iterasi sebanyak n kali, dimana n adalah panjang dari matrix A. Pada setiap iterasi, algoritma akan mengalikan elemen-elemen yang berada pada baris dan kolom yang sama pada matrix A, lalu menjumlahkan hasil perkalian tersebut, dan memasukkan hasil perkalian ke dalam matrix C.

Untuk melakukan operasi perkalian matrix, kita dapat menggunakan fungsi multiply_matrix seperti pada contoh di bawah ini.

```python
A = [
    [1, 2],
    [3, 4]
]

B = [
    [5, 6],
    [7, 8]
]

C = multiply_matrix(A, B)
print(C) # [[19, 22], [43, 50]]
```

> Informasi: Apakah ada Pembagian Matrix? Secara matematis, pembagian matrix tidak dapat dilakukan. Hal ini dikarenakan operasi pembagian matrix tidak memiliki definisi yang jelas. Cara yang lebih tepat untuk melakukan operasi pembagian matrix adalah dengan mengalikan matrix pertama dengan invers dari matrix kedua.

### Konsep Determinan Matrix

Determinan matrix adalah nilai yang diperoleh dari suatu matrix dengan aturan tertentu. Determinan hanya dapat diperoleh dari matrix yang berbentuk persegi (matriks bujursangkar). Untuk matrix berordo 2x2, determinan dapat diperoleh dengan cara mengalikan elemen-elemen pada diagonal utama, lalu mengurangkan hasil perkalian tersebut dengan hasil perkalian elemen-elemen pada diagonal kedua. Untuk matrix berordo 3x3 atau lebih, determinan dapat diperoleh dengan cara mengalikan elemen-elemen pada baris pertama dengan kofaktor masing-masing elemen tersebut, lalu menjumlahkan hasil perkalian tersebut.

Determinan matrix dapat diilustrasikan sebagai berikut:

```plaintext
A = | 1 2 |   det(A) = 1*4 - 2*3 = -2
    | 3 4 |
```

Pada contoh di atas, matrix A memiliki ukuran 2x2. Determinan matrix A diperoleh dengan cara mengalikan elemen-elemen pada diagonal utama, lalu mengurangkan hasil perkalian tersebut dengan hasil perkalian elemen-elemen pada diagonal kedua. Sehingga, determinan matrix A adalah -2.

### Algoritma Mencari Determinan Matrix

Algoritma mencari determinan matrix dapat diilustrasikan sebagai berikut:

```python
def determinant_matrix(A):
    if len(A) == 2:
        return A[0][0] * A[1][1] - A[0][1] * A[1][0]
    else:
        det = 0
        for i in range(len(A)):
            minor = [row[:i] + row[i+1:] for row in A[1:]]
            det += (-1) ** i * A[0][i] * determinant_matrix(minor)
        return det
```

Pada contoh di atas, A adalah matrix yang akan dicari determinannya. Algoritma ini akan melakukan iterasi sebanyak n kali, dimana n adalah panjang dari matrix A. Pada setiap iterasi, algoritma akan mengalikan elemen-elemen pada baris pertama dengan kofaktor masing-masing elemen tersebut, lalu menjumlahkan hasil perkalian tersebut.

Untuk melakukan operasi mencari determinan matrix, kita dapat menggunakan fungsi determinant_matrix seperti pada contoh di bawah ini.

```python
A = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

det_A = determinant_matrix(A)
print(det_A) # 0
```

## Tugas

1. Buatlah program untuk mengimplementasikan operasi perkalian matrix menggunakan bahasa pemrograman Python.
2. Buatlah program untuk mengimplementasikan operasi mencari determinan matrix menggunakan bahasa pemrograman Python.
