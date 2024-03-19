# Modul 2 - List

## Tujuan Pembelajaran

1. Siswa memahami konsep list
2. Siswa mampu membuat list
3. Siswa mampu mengakses elemen list
4. Siswa mampu mengubah elemen list
5. Siswa mampu menambah elemen list
6. Siswa mampu menghapus elemen list

## Materi

### Konsep List

List adalah jenis kumpulan data terurut (ordered sequence), dan merupakan salah satu variabel yang sering digunakan pada Python. Serupa, namun tak sama dengan array pada bahasa pemrograman lainnya. Bedanya, elemen List pada Python tidak harus memiliki tipe data yang sama. Mendeklarasikan List cukup mudah dengan kurung siku dan elemen yang dipisahkan dengan koma.

```python
contoh_list = [1, 'dua', 3, 4.0, 5]
```

### Membuat List

Untuk membuat list, kita dapat mendeklarasikan variabel dengan nilai list yang diinginkan.

```python
contoh_list = [1, 2, 3, 4, 5]

print(contoh_list)
```

### Mengakses Elemen List

List pada Python, seperti pada bahasa pemrograman umumnya, diindeks mulai dari 0. Untuk mengakses elemen tertentu pada List, kita dapat menggunakan kurung siku dan indeks dari elemen yang bersangkutan.

```python
contoh_list = [1, 2, 3, 4, 5]

elemen_pertama = contoh_list[0]
elemen_terakhir = contoh_list[-1]

print(elemen_pertama) # 1
print(elemen_terakhir) # 5
```

Pada contoh di atas, `elemen_pertama` akan bernilai 1, dan `elemen_terakhir` akan bernilai 5. Jika indeks yang diakses bernilai negatif, maka akan dihitung dari belakang, sehingga -1 merujuk pada elemen paling belakang. Dalam hal ini, -1 merujuk pada elemen 5. Untuk mengetahui panjang List, kita dapat menggunakan fungsi `len`.

```python
contoh_list = [1, 2, 3, 4, 5]

print(len(contoh_list)) # 5
```

Ekspresi dalam kurung siku pada List juga dapat berupa ekspresi matematika.

```python
contoh_list = [1, 2, 3, 4, 5]

elemen_pertama = contoh_list[1+1]
print(elemen_pertama) # 3
```

Dengan perulangan, kita dapat mengakses semua elemen pada List.

```python
contoh_list = [1, 2, 3, 4, 5]

for elemen in contoh_list:
    print(elemen)
```

#### Slicing List

Jika kita ingin mengakses elemen dari indeks ke-n sampai ke-m, maka kita dapat menggunakan _slicing_ (pemotongan) dengan menggunakan tanda `:`.

```python
contoh_list = [1, 2, 3, 4, 5]

slicing_elemen = contoh_list[1:4] # [2, 3, 4]
slicing_elemen2 = contoh_list[:4] # [1, 2, 3, 4]
slicing_elemen3 = contoh_list[1:] # [2, 3, 4, 5]

print(slicing_elemen)
```

Pada contoh di atas, `slicing_elemen` akan berisi list `[2, 3, 4]`, karena kita memotong list mulai dari indeks ke-1 hingga sebelum indeks ke-4. Sedangkan `slicing_elemen2` akan berisi list `[1, 2, 3, 4]`, karena kita memotong list mulai dari indeks ke-0 hingga sebelum indeks ke-4. Begitu pula `slicing_elemen3`, karena kita memotong list mulai dari indeks ke-1 hingga indeks terakhir.

### Mengubah Elemen List

Untuk mengubah elemen List, kita dapat melakukan pengisian ulang nilai pada indeks yang bersangkutan.

```python
contoh_list = [1, 2, 3, 4, 5]

contoh_list[0] = 10
print(contoh_list) # [10, 2, 3, 4, 5]
```

### Menambah

Untuk menambah elemen pada List, kita dapat menggunakan method `append` atau operator `+`.

```python
contoh_list = [1, 2, 3, 4, 5]

contoh_list.append(6)
print(contoh_list) # [1, 2, 3, 4, 5, 6]

contoh_list = contoh_list + [7]
print(contoh_list) # [1, 2, 3, 4, 5, 6, 7]
```

### Menghapus Elemen List

Untuk menghapus elemen List, kita dapat menggunakan method `remove` atau `pop`.

```python
contoh_list = [7, 4, 2, 1, 3, 6, 5]

contoh_list.remove(3)
print(contoh_list) # [7, 4, 2, 1, 6, 5]

elemen_yang_dihapus = contoh_list.pop(1)
print(contoh_list) # [7, 2, 1, 6, 5]
print(elemen_yang_dihapus) # 4
```

Anda perhatikan bahwa: 
- Method `remove` menghapus elemen List __berdasarkan nilainya__, sehingga jika terdapat beberapa elemen dengan nilai yang sama, __hanya elemen yang pertama kali__ ditemui yang akan dihapus. 
- Method `pop` menghapus elemen List berdasarkan indeksnya. 
- Jika method `pop` dipanggil tanpa indeks, maka method `pop` akan menghapus elemen terakhir. 
- Fungsi `pop` akan mengembalikan nilai dari elemen yang dihapus.

## Tugas

1. Buatlah list yang berisi 5 angka pertama (1, 2, 3, 4, 5)
2. Tanpa mengubah list, print 3 elemen pertama dari list
3. Dengan menggunakan slicing, ambil 3 elemen pertama dari list
4. Dengan menggunakan metode append, tambahkan angka 6 pada list
5. Dengan menggunakan metode remove, hapus angka 3 pada list
6. Dengan menggunakan metode pop, hapus angka terakhir pada list
7. Print panjang list

---

1. Buatlah list yang berisi 5 nama buah
2. Dengan menggunakan metode append, tambahkan 2 nama buah pada list
3. Dengan menggunakan metode remove, hapus 1 nama buah pada list
4. Dengan menggunakan metode pop, hapus nama buah terakhir pada list
5. Print panjang list











