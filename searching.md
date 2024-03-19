# Modul 5 - Sequential and Binary Search

## Tujuan Pembelajaran

1. Siswa memahami konsep algoritma Sequential Search
2. Siswa mampu mengimplementasikan algoritma Sequential Search
3. Siswa memahami konsep algoritma Binary Search
4. Siswa mampu mengimplementasikan algoritma Binary Search

## Materi

### Sequential Search

Sequential Search adalah algoritma pencarian sederhana yang bekerja dengan cara membandingkan setiap elemen dalam suatu list secara berurutan, hingga elemen yang dicari ditemukan. Algoritma ini akan terus mengulang langkah tersebut sampai elemen yang dicari ditemukan atau tidak ada lagi elemen yang tersisa. Algoritma ini dinamakan Sequential Search karena elemen-elemen dalam list akan diakses secara berurutan.

Konsep algoritma Sequential Search dapat diilustrasikan sebagai berikut:

1. Bandingkan elemen pertama dari list dengan elemen yang dicari.
2. Jika elemen pertama sama dengan elemen yang dicari, maka kembalikan indeks elemen pertama.
3. Jika elemen pertama tidak sama dengan elemen yang dicari, maka bandingkan elemen kedua dengan elemen yang dicari.
4. Ulangi langkah 3 sampai elemen yang dicari ditemukan atau tidak ada lagi elemen yang tersisa.

Kompleksitas waktu dari algoritma Sequential Search adalah `O(n)` yang artinya algoritma ini akan memerlukan waktu yang lama untuk list yang besar.

```python
def sequential_search(arr, x):
    for i in range(len(arr)):
        if arr[i] == x:
            return i
    return -1
```

Pada contoh di atas, `arr` adalah list yang akan dicari, dan `x` adalah elemen yang dicari. Algoritma ini akan melakukan iterasi sebanyak `n` kali, dimana `n` adalah panjang dari list `arr`. Pada setiap iterasi, algoritma akan membandingkan setiap elemen dengan elemen yang dicari. Algoritma akan mengembalikan indeks elemen yang dicari jika ditemukan, dan mengembalikan -1 jika tidak ditemukan.

Untuk mencari elemen dalam list dengan algoritma Sequential Search, kita dapat menggunakan fungsi `sequential_search` seperti pada contoh di bawah ini.

```python
arr = [64, 34, 25, 12, 22, 11, 90]

index = sequential_search(arr, 25)
print(index) # 2
```

Beberapa kelebihan dari algoritma Sequential Search adalah sederhana dan mudah diimplementasikan. Namun, algoritma ini memiliki kompleksitas waktu yang besar, sehingga tidak efisien untuk list yang besar. Sebagai contoh, algoritma ini akan memerlukan waktu yang lama untuk list yang elemen yang dicari berada di akhir list. Selain itu, algoritma ini juga tidak efisien untuk list yang elemen yang dicari tidak ada.

### Binary Search

Binary Search adalah algoritma pencarian yang bekerja dengan cara membandingkan elemen tengah dari suatu list dengan elemen yang dicari. Algoritma ini akan terus mengulang langkah tersebut sampai elemen yang dicari ditemukan atau tidak ada lagi elemen yang tersisa. Algoritma ini dinamakan Binary Search karena elemen-elemen dalam list akan diakses secara berurutan. Algoritma ini hanya dapat digunakan pada list yang sudah terurut.

Konsep algoritma Binary Search dapat diilustrasikan sebagai berikut:

1. Bandingkan elemen tengah dari list dengan elemen yang dicari.
2. Jika elemen tengah sama dengan elemen yang dicari, maka kembalikan indeks elemen tengah.
3. Jika elemen tengah lebih kecil dari elemen yang dicari, maka bandingkan elemen tengah dengan elemen di sebelah kanan.
4. Jika elemen tengah lebih besar dari elemen yang dicari, maka bandingkan elemen tengah dengan elemen di sebelah kiri.
5. Ulangi langkah 2 sampai 4 sampai elemen yang dicari ditemukan atau tidak ada lagi elemen yang tersisa.

Kompleksitas waktu dari algoritma Binary Search adalah `O(log n)` yang artinya algoritma ini akan memerlukan waktu yang cepat untuk list yang besar.

```python
def binary_search(arr, x):
    low = 0
    high = len(arr) - 1
    mid = 0

    while low <= high:
        mid = (high + low) // 2

        if arr[mid] < x:
            low = mid + 1
        elif arr[mid] > x:
            high = mid - 1
        else:
            return mid

    return -1
```

Pada contoh di atas, `arr` adalah list yang akan dicari, dan `x` adalah elemen yang dicari. Algoritma ini akan melakukan iterasi sebanyak `log n` kali, dimana `n` adalah panjang dari list `arr`. Pada setiap iterasi, algoritma akan membandingkan elemen tengah dengan elemen yang dicari. Algoritma akan mengembalikan indeks elemen yang dicari jika ditemukan, dan mengembalikan -1 jika tidak ditemukan.

Untuk mencari elemen dalam list dengan algoritma Binary Search, kita dapat menggunakan fungsi `binary_search` seperti pada contoh di bawah ini.

```python
arr = [11, 12, 22, 25, 34, 64, 90]

index = binary_search(arr, 25)
print(index) # 3
```

Beberapa kelebihan dari algoritma Binary Search adalah efisien untuk list yang besar, karena kompleksitas waktu yang cepat. Namun, algoritma ini hanya dapat digunakan pada list yang sudah terurut, sehingga tidak efisien untuk list yang belum terurut. Selain itu, algoritma ini juga tidak efisien untuk list yang elemen yang dicari tidak ada. 

## Tugas

1. Buatlah program untuk mencari elemen dalam list dengan algoritma Sequential Search.
2. Buatlah program untuk mencari elemen dalam list dengan algoritma Binary Search.
3. Ujilah kedua program tersebut dengan beberapa kasus uji yang berbeda.

## Bonus

- List pada Python, seperti pada bahasa pemrograman umumnya, memiliki beberapa metode bawaan yang dapat digunakan untuk pencarian, seperti `index` dan `count`. Coba cari tahu cara penggunaan metode tersebut.