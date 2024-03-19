Modul 6 - List Multidimensi

## Tujuan Pembelajaran

1. Siswa memahami konsep list multidimensi
2. Siswa mampu membuat list multidimensi
3. Siswa mampu mengakses elemen list multidimensi
4. Siswa mampu mengubah elemen list multidimensi
5. Siswa mampu menambah elemen list multidimensi
6. Siswa mampu menghapus elemen list multidimensi

## Materi

### Konsep List Multidimensi

List multidimensi adalah jenis kumpulan data terurut (ordered sequence) dengan dua atau lebih dimensi. List ini sering digunakan untuk merepresentasikan matriks, atau tabel dengan baris dan kolom. List multidimensi pada Python dapat diwakili dengan list yang berisi list lain.

```python
contoh_list = [
  [1, 2, 3], 
  [4, 5, 6], 
  [7, 8, 9]
]
```

Panjang dari list multidimensi adalah jumlah baris, dan panjang dari setiap list di dalamnya adalah jumlah kolom. Pada contoh di atas, list `contoh_list` memiliki panjang 3, dan setiap list di dalamnya memiliki panjang 3. Dapat dilihat bahwa list `contoh_list` merepresentasikan matriks 3x3.

Jumlah baris dan kolom dari list multidimensi dapat dihitung dengan menggunakan fungsi `len`.

```python
contoh_list = [
  [1, 2, 3], 
  [4, 5, 6], 
  [7, 8, 9]
]

jumlah_baris = len(contoh_list)
jumlah_kolom = len(contoh_list[0])

print(jumlah_baris) # 3
print(jumlah_kolom) # 3
```

### Membuat List Multidimensi

Untuk membuat list multidimensi, kita dapat mendeklarasikan variabel dengan nilai list yang diinginkan.

```python
# 3x3 matrix
contoh_list = [
  [1, 2, 3], 
  [4, 5, 6], 
  [7, 8, 9]
]

# 3x2 matrix
contoh_list2 = [
  [1, 2], 
  [3, 4], 
  [5, 6]
]

# 2x3 matrix
contoh_list3 = [
  [1, 2, 3], 
  [4, 5, 6]
]

# 1x3 matrix
contoh_list4 = [
  [1, 2, 3]
]
```

### Mengakses Elemen List Multidimensi

Untuk mengakses elemen list multidimensi, kita dapat menggunakan kurung siku dan indeks dari elemen yang bersangkutan.

```python
contoh_list = [
  [1, 2, 3], 
  [4, 5, 6], 
  [7, 8, 9]
]

elemen = contoh_list[1][1]
print(elemen) # 5
```

Pada contoh di atas, `elemen` akan bernilai 5. Elemen pada baris ke-2 dan kolom ke-2 dari list `contoh_list` diakses dengan `contoh_list[1][1]`.

### Mengubah Elemen List Multidimensi

Untuk mengubah elemen list multidimensi, kita dapat menggunakan kurung siku dan indeks dari elemen yang bersangkutan.

```python
contoh_list = [
  [1, 2, 3], 
  [4, 5, 6], 
  [7, 8, 9]
]

contoh_list[1][1] = 10

print(contoh_list)
```

Pada contoh di atas, elemen pada baris ke-2 dan kolom ke-2 dari list `contoh_list` diubah menjadi 10. Hasilnya adalah `[[1, 2, 3], [4, 10, 6], [7, 8, 9]]`.

### Menambah Elemen List Multidimensi

Untuk menambah elemen pada list multidimensi, kita dapat menggunakan method `append` atau operator `+`.

```python
contoh_list = [
  [1, 2, 3], 
  [4, 5, 6], 
  [7, 8, 9]
]

contoh_list.append([10, 11, 12])

print(contoh_list)
```

Pada contoh di atas, list `[10, 11, 12]` ditambahkan ke dalam list `contoh_list`. Hasilnya adalah `[[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12]]`.

### Menghapus Elemen List Multidimensi

Untuk menghapus elemen pada list multidimensi, kita dapat menggunakan method `pop` atau operator `del`.

```python
contoh_list = [
  [1, 2, 3], 
  [4, 5, 6], 
  [7, 8, 9]
]

contoh_list.pop(1)

print(contoh_list)
```

Pada contoh di atas, elemen pada baris ke-2 dari list `contoh_list` dihapus. Hasilnya adalah `[[1, 2, 3], [7, 8, 9]]`. Untuk menghapus elemen pada kolom ke-n, kita dapat menggunakan perulangan untuk menghapus elemen pada baris ke-n dari setiap list di dalam list. Karena di Python tidak ada tipe data matriks, maka list multidimensi pada Python tidak harus memiliki jumlah kolom yang sama untuk setiap barisnya. Hal ini berbeda dengan matriks pada bahasa pemrograman lain seperti C atau Java, dimana matriks harus memiliki jumlah kolom yang sama untuk setiap barisnya.

## Tugas

1. Buatlah list multidimensi yang merepresentasikan matriks 3x3.
2. Buatlah list multidimensi yang merepresentasikan matriks 4x4.
3. Buatlah list multidimensi yang merepresentasikan matriks 2x2.
4. Buatlah list multidimensi yang merepresentasikan matriks 3x2.
5. Buatlah list multidimensi yang merepresentasikan matriks 2x3.
6. Buatlah list multidimensi yang merepresentasikan matriks 1x3.
7. Buatlah program untuk mengakses elemen pada baris ke-2 dan kolom ke-2 dari matriks 3x3.
8. Buatlah program untuk mengubah elemen pada baris ke-2 dan kolom ke-2 dari matriks 3x3 menjadi 10.
9. Buatlah program untuk menambahkan list `[10, 11, 12]` ke dalam matriks 3x3.
10. Buatlah program untuk menghapus elemen pada baris ke-2 dari matriks 3x3.








