# Modul 3 - Bubble and Selection Sort

## Tujuan Pembelajaran

1. Siswa memahami konsep algoritma Bubble Sort
2. Siswa mampu mengimplementasikan algoritma Bubble Sort
3. Siswa memahami konsep algoritma Selection Sort
4. Siswa mampu mengimplementasikan algoritma Selection Sort

## Materi

### Bubble Sort

Bubble Sort adalah algoritma pengurutan sederhana yang bekerja dengan cara membandingkan setiap elemen dalam suatu list secara berpasangan, kemudian menukar elemen tersebut jika urutannya salah. Algoritma ini akan terus mengulang langkah tersebut sampai tidak ada lagi elemen yang dapat ditukar. Algoritma ini dinamakan Bubble Sort karena elemen dengan nilai terbesar akan seperti gelembung dan bergerak ke arah kanan.

Konsep algoritma Bubble Sort dapat diilustrasikan sebagai berikut:

1. Bandingkan elemen pertama dengan elemen kedua.
2. Jika elemen pertama lebih besar dari elemen kedua, tukar posisi keduanya.
3. Bandingkan elemen kedua dengan elemen ketiga.
4. Ulangi langkah 2 dan 3 sampai elemen terakhir.
5. Ulangi langkah 1 sampai 4 sampai tidak ada lagi elemen yang dapat ditukar.

Kompleksitas waktu dari algoritma Bubble Sort adalah `O(n^2)` yang artinya algoritma ini akan memerlukan waktu yang lama untuk list yang besar.

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr
```

Pada contoh di atas, `arr` adalah list yang akan diurutkan. Algoritma ini akan melakukan iterasi sebanyak `n` kali, dimana `n` adalah panjang dari list `arr`. Pada setiap iterasi, algoritma akan membandingkan setiap elemen dengan elemen berikutnya, dan menukar posisi jika urutannya salah.

Untuk mengurutkan list dengan algoritma Bubble Sort, kita dapat menggunakan fungsi `bubble_sort` seperti pada contoh di bawah ini.

```python
arr = [64, 34, 25, 12, 22, 11, 90]
sorted_arr = bubble_sort(arr)
print(sorted_arr) # [11, 12, 22, 25, 34, 64, 90]
```

Beberapa kelebihan dari algoritma Bubble Sort adalah sederhana dan mudah diimplementasikan. Namun, algoritma ini memiliki kompleksitas waktu yang besar, sehingga tidak efisien untuk list yang besar. 

Salah satu optimasi yang dapat dilakukan adalah dengan menambahkan variabel `swapped` yang akan menandakan apakah ada elemen yang ditukar pada iterasi tertentu. Jika tidak ada elemen yang ditukar, maka list sudah terurut dan iterasi dapat dihentikan. Dengan optimasi ini, algoritma Bubble Sort dapat berhenti lebih cepat jika list sudah terurut.

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        swapped = False
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
                swapped = True
        if not swapped:
            break
    return arr
```

#### FAQ

1. **Apa kelebihan dari algoritma Bubble Sort?**
   
   Algoritma Bubble Sort memiliki kelebihan yaitu sederhana dan mudah diimplementasikan.

2. **Apa kekurangan dari algoritma Bubble Sort?**

   Algoritma Bubble Sort memiliki kompleksitas waktu yang besar, sehingga tidak efisien untuk list yang besar.

3. ** Kapan algoritma Bubble Sort sering digunakan?**

   Algoritma Bubble Sort sering digunakan untuk keperluan pendidikan dan pembelajaran karena sederhana dan mudah diimplementasikan.

### Selection Sort

Selection Sort adalah algoritma pengurutan sederhana yang bekerja dengan cara mencari elemen terkecil atau terbesar dari list, kemudian menempatkannya di posisi paling depan atau paling belakang. Algoritma ini akan terus mencari elemen terkecil atau terbesar dari sisa list yang belum terurut, dan menempatkannya di posisi yang sesuai. Algoritma ini dapat mengurutkan data dari besar ke kecil (ascending) atau sebaliknya (descending).

Konsep algoritma Selection Sort dapat diilustrasikan sebagai berikut:

1. Cari elemen terkecil dari list.
2. Tukar elemen terkecil dengan elemen pertama.
3. Cari elemen terkecil dari sisa list.
4. Tukar elemen terkecil dengan elemen kedua.
5. Ulangi langkah 3 dan 4 sampai list terurut.

Kompleksitas waktu dari algoritma Selection Sort adalah `O(n^2)` yang artinya algoritma ini akan memerlukan waktu yang lama untuk list yang besar.

```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        min_idx = i # indeks elemen terkecil
        for j in range(i+1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
    return arr
```

Pada contoh di atas, `arr` adalah list yang akan diurutkan. Algoritma ini akan melakukan iterasi sebanyak `n` kali, dimana `n` adalah panjang dari list `arr`. Pada setiap iterasi, algoritma akan mencari elemen terkecil dari sisa list yang belum terurut, dan menukar posisi elemen terkecil dengan elemen pertama dari sisa list.

Untuk mengurutkan list dengan algoritma Selection Sort, kita dapat menggunakan fungsi `selection_sort` seperti pada contoh di bawah ini.

```python
arr = [64, 34, 25, 12, 22, 11, 90]
sorted_arr = selection_sort(arr)
print(sorted_arr) # [11, 12, 22, 25, 34, 64, 90]
```

Beberapa kelebihan dari algoritma Selection Sort adalah sederhana dan mudah diimplementasikan. Namun, algoritma ini memiliki kompleksitas waktu yang besar, sehingga tidak efisien untuk list yang besar. Selain itu, algoritma ini tidak efisien untuk list yang sudah hampir terurut dan tidak stabil jika terdapat elemen dengan nilai yang sama.

#### FAQ

1. **Apa kelebihan dari algoritma Selection Sort?**
   
   Algoritma Selection Sort memiliki kelebihan yaitu sederhana dan mudah diimplementasikan.

2. **Apa kekurangan dari algoritma Selection Sort?**

   Algoritma Selection Sort memiliki kompleksitas waktu yang besar, sehingga tidak efisien untuk list yang besar. Selain itu, algoritma ini tidak efisien untuk list yang sudah hampir terurut dan tidak stabil jika terdapat elemen dengan nilai yang sama.

3. ** Kapan algoritma Selection Sort sering digunakan?**

   Algoritma Selection Sort sering digunakan untuk keperluan pendidikan dan pembelajaran karena sederhana dan mudah diimplementasikan.

## Tugas

1. Buatlah sebuah fungsi `bubble_sort` untuk mengurutkan list menggunakan algoritma Bubble Sort.
2. Buatlah sebuah fungsi `selection_sort` untuk mengurutkan list menggunakan algoritma Selection Sort.
3. Uji kedua fungsi tersebut dengan list yang berisi angka acak menggunakan `timeit` untuk mengukur waktu eksekusi kedua fungsi tersebut.

### Contoh fungsi Acak

```python
import random

def generate_random_list(length):
    return [random.randint(0, 1000) for i in range(length)]

arr = generate_random_list(1000)
```
