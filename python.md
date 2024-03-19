# Dasar-dasar Python

## Tujuan Pembelajaran

1. Siswa memahami konsep variable, tipe data, dan operator
2. Siswa memahami konsep percabangan
3. Siswa memahami konsep perulangan
4. Siswa mampu membuat program sederhana

## Materi

### Variable

Variable adalah tempat penyimpanan yang dapat digunakan untuk menampung sebuah data atau informasi. Sebagai contoh, kita dapat membuat sebuah variable dengan nama `bilangan1` dan memberikan nilai `5` kepadanya.

```python
bilangan1 = 5

print(bilangan1) # 5
```

Pada contoh di atas, kita membuat sebuah variable `bilangan1` yang menyimpan nilai `5`. Kemudian kita mencetak nilai dari variable tersebut dengan menggunakan fungsi `print`. Hasilnya akan mencetak nilai `5`. Nilai dalam variable dapat diubah sewaktu-waktu.

```python
bilangan1 = 5
print(bilangan1) # 5

bilangan1 = 10
print(bilangan1) # 10
```

Pada contoh di atas, kita mengubah nilai dari variable `bilangan1` menjadi `10`. Hasilnya akan mencetak nilai `5` dan `10`.

> Informasi: Pada Python, kita tidak perlu mendeklarasikan tipe data dari variable. Python akan secara otomatis menyesuaikan tipe data dari variable sesuai dengan nilai yang diberikan. Nama variable pada Python dapat diawali dengan huruf atau garis bawah, dan dapat terdiri dari huruf, angka, dan garis bawah.

#### Komentar

Komentar adalah bagian dari kode yang tidak akan dieksekusi oleh program. Komentar biasanya digunakan untuk memberikan penjelasan atau dokumentasi pada kode. Komentar pada Python dapat ditulis dengan menggunakan tanda `#`.

```python
# Ini adalah komentar
print("Hello, World!")
```

### Tipe Data

Tipe data adalah kumpulan tipe yang dapat digunakan oleh suatu variable. Pada Python, tipe data terdiri dari:

1. __Angka (integer, float)__
2. __String__
3. Sequence (list, tuple, range)
4. Mapping (dictionary)
5. Set (set, frozenset)
6. __Boolean (True, False)__
7. Binary (bytes, bytearray, memoryview)

Pada halaman ini, kita akan membahas tipe data angka, string dan boolean saja.

#### Angka

Tipe data angka terdiri dari bilangan bulat (integer) dan bilangan desimal (float).

```python
bilangan_bulat = 5
bilangan_desimal = 3.14

print(bilangan_bulat) # 5
print(bilangan_desimal) # 3.14
```

#### String

Tipe data string adalah kumpulan karakter. String dapat ditulis dengan menggunakan tanda kutip satu (`'`) atau tanda kutip dua (`"`).

```python
kalimat1 = 'Ini adalah string'
kalimat2 = "Ini juga string"

print(kalimat1) # Ini adalah string
print(kalimat2) # Ini juga string
```

String juga dapat ditulis dengan menggunakan tanda kutip tiga (`'''` atau `"""`) untuk string yang panjang.

```python
kalimat_panjang = '''Ini adalah string yang panjang.
String ini ditulis dengan menggunakan tanda kutip tiga.
'''

print(kalimat_panjang)
```

#### Boolean

Tipe data boolean adalah tipe data yang hanya memiliki dua nilai, yaitu `True` dan `False`.

```python
benar = True
salah = False

print(benar) # True
print(salah) # False
```

#### Konversi Tipe Data

Pada Python, kita dapat mengonversi tipe data dengan menggunakan fungsi bawaan Python, seperti `int`, `float`, `str`, dan lain sebagainya.

```python
angka = 5
angka_string = str(angka)

print(angka) # 5
print(angka_string) # '5'
```

### Operator

Operator adalah simbol-simbol yang dapat digunakan untuk melakukan operasi tertentu. Pada Python, operator terdiri dari:

1. __Operator Aritmatika__
2. __Operator Perbandingan__
3. __Operator Logika__
4. Operator Penugasan
5. Operator Membership
6. Operator Identitas

Pada halaman ini, kita akan membahas operator aritmatika, perbandingan, dan logika saja.

#### Operator Aritmatika

Operator aritmatika digunakan untuk melakukan operasi matematika.

```python
bilangan1 = 5
bilangan2 = 2

jumlah = bilangan1 + bilangan2
kurang = bilangan1 - bilangan2
kali = bilangan1 * bilangan2
bagi = bilangan1 / bilangan2
modulus = bilangan1 % bilangan2
pangkat = bilangan1 ** bilangan2

print(jumlah) # 7
print(kurang) # 3
print(kali) # 10
print(bagi) # 2.5
print(modulus) # 1
print(pangkat) # 25
```

#### Operator Perbandingan

Operator perbandingan digunakan untuk membandingkan dua buah nilai. Pada umumnya, hasil dari operasi perbandingan adalah tipe data boolean (`True` atau `False`).

```python
bilangan1 = 5
bilangan2 = 2

sama_dengan = bilangan1 == bilangan2
tidak_sama_dengan = bilangan1 != bilangan2
lebih_besar = bilangan1 > bilangan2
kurang_dari = bilangan1 < bilangan2
lebih_besar_sama_dengan = bilangan1 >= bilangan2
kurang_dari_sama_dengan = bilangan1 <= bilangan2

print(sama_dengan) # False
print(tidak_sama_dengan) # True
print(lebih_besar) # True
print(kurang_dari) # False
print(lebih_besar_sama_dengan) # True
print(kurang_dari_sama_dengan) # False
```

#### Operator Logika

Operator logika digunakan untuk menggabungkan beberapa nilai kebenaran dari suatu pernyataan logika. Pada Python, operator logika terdiri dari `and`, `or`, dan `not`.

```python
benar = True
salah = False

logika_and = benar and salah
logika_or = benar or salah
logika_not = not benar

print(logika_and) # False
print(logika_or) # True
print(logika_not) # False
```

### Percabangan

Percabangan adalah struktur kontrol yang digunakan untuk mengambil keputusan. Pada Python, percabangan terdiri dari `if`, `elif`, dan `else`.

```python
bilangan = 5

if bilangan > 0:
    print("Bilangan positif")
elif bilangan < 0:
    print("Bilangan negatif")
else:
    print("Bilangan nol")
```

Pada contoh di atas, jika `bilangan` lebih besar dari `0`, maka program akan mencetak `Bilangan positif`. Jika tidak, maka program akan mengecek kondisi berikutnya, yaitu apakah `bilangan` kurang dari `0`. Jika benar, maka program akan mencetak `Bilangan negatif`. Jika tidak, maka program akan mencetak `Bilangan nol`.

### Perulangan

Perulangan adalah struktur kontrol yang digunakan untuk mengulangi blok kode tertentu. Pada Python, perulangan terdiri dari `for` dan `while`.

#### Perulangan `for`

Perulangan `for` digunakan untuk mengulangi kode secara terurut.

```python
for i in range(5):
    print(i)
```

Pada contoh di atas, program akan mencetak angka dari `0` hingga `4`. Fungsi `range` digunakan untuk membuat deret angka. 
- Kata kunci `in` digunakan untuk mengakses setiap elemen dari deret angka tersebut. 
- Variabel `i` akan menyimpan nilai dari setiap elemen deret angka.

#### Perulangan `while`

Perulangan `while` digunakan untuk mengulangi kode selama kondisi tertentu terpenuhi.

```python
i = 0

while i < 5:
    print(i)
    i += 1
```

Pada contoh di atas, program akan mencetak angka dari `0` hingga `4`. Kondisi `i < 5` akan mengecek apakah nilai dari `i` kurang dari `5`. Jika benar, maka program akan mencetak nilai dari `i` dan menambahkan `1` ke nilai `i`. Proses ini akan terus berulang hingga kondisi `i < 5` tidak terpenuhi.

## Latihan

1. Buatlah sebuah program yang meminta input dari user berupa nama dan umur, kemudian mencetak nama dan umur yang telah dimasukkan. 
- Jika umur yang dimasukkan kurang dari `0`, maka program akan mencetak pesan kesalahan.
- Jika umur yang dimasukkan lebih dari `100`, maka program akan mencetak pesan kesalahan.

__Hint:__ Gunakan fungsi `input` untuk meminta input dari user.





