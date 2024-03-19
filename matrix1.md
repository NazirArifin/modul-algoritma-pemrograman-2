# Modul 7 - Operasi Matrix (Penjumlahan, Pengurangan)

## Tujuan Pembelajaran

1. Siswa memahami konsep operasi penjumlahan dan pengurangan matrix
2. Siswa mampu melakukan operasi penjumlahan dan pengurangan matrix
3. Siswa mampu menganalisis kompleksitas algoritma penjumlahan dan pengurangan matrix

## Materi

### Konsep Operasi Matrix

Operasi penjumlahan dan pengurangan matrix adalah operasi yang dilakukan pada dua buah matrix. Operasi ini dilakukan dengan cara menjumlahkan atau mengurangkan elemen-elemen yang berada pada posisi yang sama pada kedua matrix. Operasi ini hanya dapat dilakukan pada matrix yang memiliki ukuran yang sama.

Operasi penjumlahan dan pengurangan matrix dapat diilustrasikan sebagai berikut:

```plaintext
A = | 1 2 |   B = | 3 4 |   A + B = | 4  6  |
    | 5 6 |       | 7 8 |           | 12 14 |
```

Pada contoh di atas, matrix `A` dan `B` memiliki ukuran yang sama, yaitu 2x2. Operasi penjumlahan matrix `A` dan `B` dilakukan dengan cara menjumlahkan elemen-elemen yang berada pada posisi yang sama pada kedua matrix. Sehingga, hasil penjumlahan matrix `A` dan `B` adalah matrix `C` yang memiliki elemen-elemen yang merupakan hasil penjumlahan elemen-elemen matrix `A` dan `B`.

### Algoritma Penjumlahan dan Pengurangan Matrix

Algoritma penjumlahan dan pengurangan matrix dapat diilustrasikan sebagai berikut:

```python
def add_matrix(A, B):
    C = []
    for i in range(len(A)):
        row = []
        for j in range(len(A[0])):
            row.append(A[i][j] + B[i][j])
        C.append(row)
    return C
```

Pada contoh di atas, `A` dan `B` adalah dua buah matrix yang akan dijumlahkan. Algoritma ini akan melakukan iterasi sebanyak `n` kali, dimana `n` adalah panjang dari matrix `A`. Pada setiap iterasi, algoritma akan menjumlahkan elemen-elemen yang berada pada posisi yang sama pada kedua matrix, dan memasukkan hasil penjumlahan ke dalam matrix `C`.

Untuk melakukan operasi penjumlahan matrix, kita dapat menggunakan fungsi `add_matrix` seperti pada contoh di bawah ini.

```python
A = [
    [1, 2],
    [3, 4]
]

B = [
    [5, 6],
    [7, 8]
]

C = add_matrix(A, B)
print(C) # [[6, 8], [10, 12]]
```

Algoritma pengurangan matrix dapat diilustrasikan sebagai berikut:

```python
def subtract_matrix(A, B):
    C = []
    for i in range(len(A)):
        row = []
        for j in range(len(A[0])):
            row.append(A[i][j] - B[i][j])
        C.append(row)
    return C
```

Pada contoh di atas, `A` dan `B` adalah dua buah matrix yang akan dikurangkan. Algoritma ini akan melakukan iterasi sebanyak `n` kali, dimana `n` adalah panjang dari matrix `A`. Pada setiap iterasi, algoritma akan mengurangkan elemen-elemen yang berada pada posisi yang sama pada kedua matrix, dan memasukkan hasil pengurangan ke dalam matrix `C`.

Untuk melakukan operasi pengurangan matrix, kita dapat menggunakan fungsi `subtract_matrix` seperti pada contoh di bawah ini.

```python
A = [
    [1, 2],
    [3, 4]
]

B = [
    [5, 6],
    [7, 8]
]

C = subtract_matrix(A, B)
print(C) # [[-4, -4], [-4, -4]]
```

### Analisis Kompleksitas Algoritma

Kompleksitas waktu dari algoritma penjumlahan dan pengurangan matrix adalah `O(n^2)` yang artinya algoritma ini akan memerlukan waktu yang lama untuk matrix yang besar. Hal ini disebabkan oleh iterasi sebanyak `n` kali, dimana `n` adalah panjang dari matrix `A`. Pada setiap iterasi, algoritma akan menjumlahkan atau mengurangkan elemen-elemen yang berada pada posisi yang sama pada kedua matrix.

## Tugas

1. Jelaskan konsep operasi penjumlahan dan pengurangan matrix!
2. Implementasikan algoritma penjumlahan dan pengurangan matrix menggunakan bahasa pemrograman Python!
3. Analisis kompleksitas algoritma penjumlahan dan pengurangan matrix!