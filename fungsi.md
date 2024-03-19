# Modul 1 - Fungsi

## Tujuan Pembelajaran

1. Mahasiswa memahami konsep fungsi.
2. Mahasiswa mampu membuat fungsi.
3. Mahasiswa mampu memanggil fungsi.

## Materi

### Konsep Fungsi

Fungsi adalah sebuah blok kode yang dapat digunakan kembali. Fungsi dapat menerima argumen dan mengembalikan nilai. Fungsi dapat digunakan untuk memecah program menjadi bagian-bagian yang lebih kecil. Fungsi juga dapat digunakan untuk __menghindari duplikasi kode__. Contoh dari fungsi adalah fungsi `len` yang digunakan untuk menghitung panjang dari sebuah list. 

Dengan menggunakan fungsi, kita dapat membuat kode yang lebih mudah dibaca dan dipahami. Selain itu, fungsi juga membuat kode bisa digunakan kembali (_reusable_) sehingga kita tidak perlu menulis kode yang sama berulang-ulang.

### Membuat Fungsi

Fungsi pada Python dibuat dengan menggunakan kata kunci `def` diikuti dengan nama fungsi dan parameter (jika ada). Nama fungsi harus diawali dengan huruf atau garis bawah `_` dan tidak boleh mengandung spasi. Umumnya, nama fungsi menggunakan huruf kecil. Berikut adalah contoh pembuatan fungsi:

```python
def sapa():
    print("Hai!")
```

Pada contoh di atas, kita membuat fungsi `sapa` yang tidak menerima parameter. Fungsi tersebut hanya mencetak "Hai!" ke layar. 

> __Penting__: Jangan lupa untuk memberikan indentasi pada blok kode di dalam fungsi. 
> Indentasi yang digunakan biasanya adalah 4 spasi atau 1 tab.
> Di Python, indentasi sangat penting karena digunakan untuk menandai blok kode. Selain itu, Python juga tidak menggunakan tanda kurung kurawal `{}` atau titik koma `;` seperti pada bahasa pemrograman lainnya.

### Memanggil Fungsi

Fungsi hanya akan dijalankan jika kita memanggilnya. Berikut adalah contoh cara memanggil fungsi `sapa`:

```python
sapa()
```

Contoh kode lengkapnya adalah sebagai berikut:

```python
def sapa():
    print("Hai!")

sapa()
```

Simpan kode di atas dalam sebuah file dengan ekstensi `.py` dan jalankan menggunakan perintah `python nama_file.py` di terminal (Linux/Mac) atau command prompt (Windows). Jika berhasil, maka akan muncul tulisan "Hai!" di layar.

### Membuat Fungsi dengan Parameter

Fungsi juga dapat menerima parameter. Parameter adalah nilai dari luar yang dimasukkan kedalam fungsi ketika fungsi tersebut dipanggil. Tidak ada batasan jumlah parameter yang dapat diterima oleh fungsi. Selain itu parameter juga bisa memiliki tipedata yang bermacam-macam (`string`, `integer`, `float`, `list`, `dictionary`, `fungsi lain`, dan lain-lain).
Berikut adalah contoh pembuatan fungsi dengan parameter:

```python
def sapa(nama):
    print("Hai, " + nama)
    # atau bisa juga dengan cara
    # print(f"Hai, {nama}")

sapa("Budi")
```

Pada contoh di atas, kita membuat fungsi `sapa` yang menerima satu parameter bernama `nama`. Fungsi tersebut akan mencetak "Hai, Budi" jika dipanggil dengan `sapa("Budi")`.

> __Penting__: Jumlah parameter yang diterima oleh fungsi harus sama dengan jumlah argumen yang diberikan ketika memanggil fungsi. Jika tidak, maka akan terjadi error.

Contoh fungsi dengan dua parameter:

```python
def tambah(a, b):
    print("Penjumlahan", a, "+", b, "=", a + b)

# panggil fungsi tambah dengan dua argumen
tambah(3, 4)
```

### Mengembalikan Nilai

Fungsi juga dapat mengembalikan nilai. Nilai yang dikembalikan oleh fungsi dapat digunakan oleh kode yang memanggil fungsi tersebut. Kata kunci yang digunakan untuk mengembalikan nilai adalah `return`.
Berikut adalah contoh fungsi yang mengembalikan nilai:

```python
def kuadrat(x):
    result = x * x
    return result

hasil = kuadrat(5)
print(hasil) # akan mencetak 25
```

Pada contoh di atas, fungsi `kuadrat` menerima satu parameter `x` dan mengembalikan nilai `x * x`. Nilai yang dikembalikan oleh fungsi tersebut kemudian disimpan dalam variabel `hasil` dan dicetak ke layar.

### Parameter Default

Fungsi juga dapat memiliki nilai default untuk parameter-parameter yang dimilikinya. Nilai default digunakan ketika fungsi dipanggil tanpa memberikan nilai untuk parameter tersebut. Berikut adalah contoh fungsi dengan nilai default:

```python
def sapa(nama=""):
    if nama == "":
        print("Hai!")
    else:
        print("Hai, " + nama + "!")

sapa() # akan mencetak "Hai!"
sapa("Budi") # akan mencetak "Hai, Budi!"
```

Pada contoh di atas, fungsi `sapa` memiliki satu parameter `nama` yang memiliki nilai default yaitu string kosong `""`. Ketika fungsi dipanggil tanpa memberikan argumen, maka fungsi akan mencetak "Hai!". Namun, jika fungsi dipanggil dengan memberikan argumen, maka fungsi akan mencetak "Hai, Budi!".

Contoh lain:

```python
def pangkat(x, n=2):
    return x ** n

print(pangkat(2)) # akan mencetak 4
print(pangkat(2, 3)) # akan mencetak 8
```

### Parameter Berdasarkan Nama

Ketika memanggil fungsi, kita dapat memberikan argumen berdasarkan nama parameternya. Dengan cara ini, kita tidak perlu memperdulikan urutan parameter ketika memanggil fungsi. Berikut adalah contoh penggunaan parameter berdasarkan nama:

```python
def sapa(nama, ucapan="Hai"):
    print(ucapan + ", " + nama + "!")

sapa(ucapan="Selamat pagi", nama="Budi") # akan mencetak "Selamat pagi, Budi!"
```

Pada contoh di atas, kita memanggil fungsi `sapa` dengan memberikan argumen berdasarkan nama parameternya. Kita memberikan argumen `ucapan` terlebih dahulu, kemudian argumen `nama`. Meskipun urutan parameter pada fungsi `sapa` adalah `nama` terlebih dahulu, kita tetap bisa memanggil fungsi dengan cara ini.

> __Penting__: Jika kita memberikan argumen berdasarkan nama, maka urutan argumen tidak lagi penting. Namun, jika kita memberikan argumen tanpa nama, maka urutan argumen menjadi penting.

### Fungsi Dengan Jumlah Parameter yang Tidak Diketahui

Fungsi juga dapat menerima jumlah parameter yang tidak diketahui. Hal ini dapat dilakukan dengan menggunakan `*` sebelum nama parameter. Berikut adalah contoh penggunaan `*`:

```python
def jumlahkan(*args):
    result = 0
    for angka in args:
        result += angka
    return result

print(jumlahkan(1, 2, 3, 4, 5)) # akan mencetak 15
print(jumlahkan(1, 2, 3)) # akan mencetak 6
```

Pada contoh di atas, fungsi `jumlahkan` menerima jumlah parameter yang tidak diketahui. Kita dapat memberikan berapapun argumen ke fungsi tersebut. Argumen-argumen tersebut akan disimpan dalam bentuk [`tuple`](https://www.w3schools.com/python/python_tuples.asp) di dalam parameter `args`. Kita dapat menggunakan `*args` untuk mengakses semua argumen yang diberikan ke fungsi tersebut.

### Fungsi Dengan Jumlah Parameter yang Tidak Diketahui Berdasarkan Nama

Fungsi juga dapat menerima jumlah parameter yang tidak diketahui berdasarkan nama. Hal ini dapat dilakukan dengan menggunakan `**` sebelum nama parameter. Berikut adalah contoh penggunaan `**`:

```python
def print_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_info(nama="Budi", umur=20, pekerjaan="guru")
```

Pada contoh di atas, fungsi `print_info` menerima jumlah parameter yang tidak diketahui berdasarkan nama. Kita dapat memberikan berapapun argumen berdasarkan nama ke fungsi tersebut. Argumen-argumen tersebut akan disimpan dalam bentuk [`dictionary`](https://www.w3schools.com/python/python_dictionaries.asp) di dalam parameter `kwargs`. Kita dapat menggunakan `**kwargs` untuk mengakses semua argumen yang diberikan ke fungsi tersebut.

### Fungsi Rekursif

Fungsi rekursif adalah fungsi yang memanggil dirinya sendiri. Fungsi rekursif biasanya digunakan untuk menyelesaikan permasalahan yang dapat dipecahkan menjadi sub-permasalahan yang lebih kecil. Berikut adalah contoh penggunaan fungsi rekursif:

```python
def faktorial(n):
    if n == 1:
        return 1
    else:
        return n * faktorial(n - 1)

print(faktorial(5)) # akan mencetak 120
```

Pada contoh di atas, fungsi `faktorial` adalah fungsi rekursif yang digunakan untuk menghitung nilai faktorial dari bilangan bulat `n`. Fungsi tersebut memanggil dirinya sendiri dengan parameter `n - 1` sampai `n` sama dengan 1.

### Fungsi bawaan Python

Python memiliki banyak fungsi bawaan yang dapat digunakan untuk mempermudah pekerjaan kita. Beberapa fungsi bawaan yang sering digunakan adalah:

- `len` : digunakan untuk menghitung panjang dari sebuah list, tuple, atau string.
- `print` : digunakan untuk mencetak nilai ke layar.
- `range` : digunakan untuk membuat list angka berurutan.
- `split` : digunakan untuk memecah string menjadi list kata-kata.
- `tolower` : digunakan untuk mengubah huruf menjadi huruf kecil.

Semua fungsi bawaan Python dapat dilihat di [dokumentasi Python](https://docs.python.org/3/library/functions.html). Anda tidak perlu menghafal semua fungsi bawaan Python, namun Anda perlu tahu bahwa fungsi-fungsi tersebut ada dan dapat digunakan.

## Tugas

1. Buatlah sebuah fungsi `hitung_kata` yang menerima satu parameter berupa string. Fungsi tersebut akan mengembalikan jumlah kata yang ada di dalam string tersebut. Kata adalah karakter yang dipisahkan oleh spasi. __Contoh__: "Halo, nama saya Budi" memiliki 4 kata. __Hint__: Gunakan fungsi `split` untuk memecah string menjadi list kata-kata.

2. Buatlah sebuah fungsi `hitung_vokal` yang menerima satu parameter berupa string. Fungsi tersebut akan mengembalikan jumlah huruf vokal yang ada di dalam string tersebut. Huruf vokal yang diperhitungkan adalah `a`, `i`, `u`, `e`, `o` baik huruf besar maupun huruf kecil. __Contoh__: "Halo, nama saya Budi" memiliki 8 huruf vokal. __Hint__: Gunakan perulangan untuk menghitung jumlah huruf vokal.

3. Buatlah sebuah fungsi `hitung_luas` yang menerima dua parameter `panjang` dan `lebar`. Fungsi tersebut menggunakan nilai default 1 untuk kedua parameter dan memiliki parameter berdasarkan nama. Fungsi tersebut akan mengembalikan hasil perkalian `panjang` dan `lebar`. __Contoh__: `hitung_luas(panjang=4, lebar=5)` akan mengembalikan nilai 20. 

4. Buatlah sebuah fungsi `cetak_semuanya` yang menerima jumlah parameter yang tidak diketahui. Fungsi tersebut akan mencetak semua argumen yang diberikan. __Contoh__: `cetak_semuanya(1, 2, 3, "Halo", "Budi")` akan mencetak:
```plaintext
1 2 3 Halo Budi
```

5. Buatlah sebuah fungsi `cetak_info` yang menerima parameter `**kwargs`. Fungsi tersebut akan mencetak semua pasangan key-value yang diberikan. __Contoh__: `cetak_info(nama="Budi", umur=20, pekerjaan="guru")` akan mencetak:
```plaintext
nama: Budi
umur: 20
pekerjaan: guru
```












