# Modul 4 - Insertion and Quick Sort

## Tujuan Pembelajaran

1. Siswa memahami konsep algoritma Insertion Sort
2. Siswa mampu mengimplementasikan algoritma Insertion Sort
3. Siswa memahami konsep algoritma Quick Sort
4. Siswa mampu mengimplementasikan algoritma Quick Sort

## Materi

### Insertion Sort

Insertion Sort adalah algoritma pengurutan sederhana yang bekerja dengan cara membandingkan setiap elemen dalam suatu list secara berpasangan, kemudian memindahkan elemen tersebut ke posisi yang tepat. Algoritma ini akan terus mengulang langkah tersebut sampai tidak ada lagi elemen yang dapat dipindahkan. Algoritma ini dinamakan Insertion Sort karena elemen-elemen yang akan diurutkan akan dimasukkan ke posisi yang tepat satu per satu.

Konsep algoritma Insertion Sort dapat diilustrasikan sebagai berikut:

1. Ambil elemen pertama dari list, elemen ini dianggap sudah terurut.
2. Ambil elemen kedua dari list, bandingkan dengan elemen pertama, dan pindahkan ke posisi yang tepat.
3. Ambil elemen ketiga dari list, bandingkan dengan elemen kedua, dan pindahkan ke posisi yang tepat.
4. Ulangi langkah 2 dan 3 sampai elemen terakhir.
5. Ulangi langkah 1 sampai 4 sampai tidak ada lagi elemen yang dapat dipindahkan.

Kompleksitas waktu dari algoritma Insertion Sort adalah `O(n^2)` yang artinya algoritma ini akan memerlukan waktu yang lama untuk list yang besar.

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i-1
        while j >= 0 and key < arr[j]:
            arr[j+1] = arr[j]
            j -= 1
        arr[j+1] = key
    return arr
```

Pada contoh di atas, `arr` adalah list yang akan diurutkan. Algoritma ini akan melakukan iterasi sebanyak `n` kali, dimana `n` adalah panjang dari list `arr`. Pada setiap iterasi, algoritma akan membandingkan setiap elemen dengan elemen sebelumnya, dan memindahkan elemen ke posisi yang tepat.

Untuk mengurutkan list dengan algoritma Insertion Sort, kita dapat menggunakan fungsi `insertion_sort` seperti pada contoh di bawah ini.

```python
arr = [64, 34, 25, 12, 22, 11, 90]
sorted_arr = insertion_sort(arr)
print(sorted_arr) # [11, 12, 22, 25, 34, 64, 90]
```

Beberapa kelebihan dari algoritma Insertion Sort adalah sederhana dan mudah diimplementasikan. Namun, algoritma ini memiliki kompleksitas waktu yang besar, sehingga tidak efisien untuk list yang besar. Sebagai contoh, algoritma ini akan memerlukan waktu yang lama untuk list yang sudah terurut secara terbalik. Selain itu, algoritma ini juga tidak efisien untuk list yang sudah terurut.

Contoh lain implementasi algoritma Insertion Sort adalah sebagai berikut:

```python
def selection_sort(arr):
    for i in range(len(arr)):
        min_index = i
        for j in range(i + 1, len(arr)):
            if arr[j] < arr[min_index]:
                min_index = j

        # Swap
        arr[i], arr[min_index] = arr[min_index], arr[i]
    return arr
```

### Quick Sort

Quick Sort adalah algoritma pengurutan yang bekerja dengan cara memilih elemen pivot dari list, kemudian mempartisi list ke dalam dua bagian, dimana elemen-elemen yang lebih kecil dari pivot akan berada di sebelah kiri pivot, dan elemen-elemen yang lebih besar dari pivot akan berada di sebelah kanan pivot. Setelah itu, algoritma akan memanggil dirinya sendiri untuk kedua bagian tersebut.

Konsep algoritma Quick Sort dapat diilustrasikan sebagai berikut:

1. Pilih elemen pivot dari list.
2. Partisi list ke dalam dua bagian, dimana elemen-elemen yang lebih kecil dari pivot akan berada di sebelah kiri pivot, dan elemen-elemen yang
    lebih besar dari pivot akan berada di sebelah kanan pivot.
3. Panggil diri sendiri untuk kedua bagian tersebut.
4. Ulangi langkah 1 sampai 3 sampai list terurut.

Kompleksitas waktu dari algoritma Quick Sort adalah `O(n log n)` yang artinya algoritma ini akan memerlukan waktu yang cepat untuk list yang besar.

```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    else:
        pivot = arr[0]
        less = [x for x in arr[1:] if x <= pivot]
        greater = [x for x in arr[1:] if x > pivot]
        return quick_sort(less) + [pivot] + quick_sort(greater)
```

Pada contoh di atas, `arr` adalah list yang akan diurutkan. Algoritma ini akan memanggil dirinya sendiri untuk kedua bagian list yang lebih kecil dari pivot dan lebih besar dari pivot. Algoritma ini akan berhenti jika panjang dari list tersebut kurang dari atau sama dengan 1.

Untuk mengurutkan list dengan algoritma Quick Sort, kita dapat menggunakan fungsi `quick_sort` seperti pada contoh di bawah ini.

```python
arr = [64, 34, 25, 12, 22, 11, 90]
sorted_arr = quick_sort(arr)
print(sorted_arr) # [11, 12, 22, 25, 34, 64, 90]
```

Beberapa kelebihan dari algoritma Quick Sort adalah kompleksitas waktu yang cepat, sehingga efisien untuk list yang besar. Namun, algoritma ini memiliki kompleksitas waktu terburuk `O(n^2)` jika list yang diurutkan sudah terurut. Selain itu, algoritma ini juga memerlukan memori tambahan untuk menampung list yang lebih kecil dari pivot dan lebih besar dari pivot.

Contoh lain implementasi algoritma Quick Sort adalah sebagai berikut:

```python
def quick_sort(arr, low, high):
    if low < high:
        pi = partition(arr, low, high)
        quick_sort(arr, low, pi-1)
        quick_sort(arr, pi+1, high)

def partition(arr, low, high):
    i = low - 1
    pivot = arr[high]

    for j in range(low, high):
        if arr[j] < pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]

    arr[i+1], arr[high] = arr[high], arr[i+1]
    return i+1
```

## Tugas

1. Implementasikan algoritma Insertion Sort dengan menggunakan bahasa pemrograman Python.
2. Implementasikan algoritma Quick Sort dengan menggunakan bahasa pemrograman Python.

## Bonus

- List pada Python, seperti pada bahasa pemrograman umumnya, memiliki beberapa metode bawaan yang dapat digunakan untuk pengurutan, seperti `sort` dan `sorted`. Coba cari tahu cara penggunaan metode tersebut.


