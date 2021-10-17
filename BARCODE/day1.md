---
title: BARCODE
author: DEFAULT UNJ
date: 2021-08-22
---

# BARCODE

## Day - 1

---

Selamat datang di pertemuan pertama BARCODE. Pada sesi kali ini kalian akan belajar beberapa hal:

- Struktur dasar program C
- Tipe data
- Operator
- Input / Output

Selamat mengikuti !

---

## Hello, World !

---

Ketika memulai belajar *programming*, program yang terkenal bagi para pemula adalah program **Hello, World!** Mari kita buat program tersebut.

---

**Program *Hello, World!***

```c
#include<stdio.h>

/*
  Berikut adalah main function
  main function diperlukan untuk setiap program
*/
int main(){

  // Cetak kalimat "Hello, World!"
  printf("Hello, World!");

  return 0;
}
```

---

## Menjalankan Program

Untuk meng-compile program yang telah kita buat, kita dapat menggunakan *command* berikut ini:
> Proses kompilasi dilakukan untuk menterjemahkan program dari bahasa tingkat tinggi (C) ke bahasa yang dimengerti oleh mesin

```bash
# Format : gcc <nama_file>.c -o <nama_file>

gcc hello_world.c -o hello_world
```

Lalu untuk menjalankannya, gunakan command berikut:

```bash
# Windows
.\hello_world

# Linux / Mac
./hello_world
```

---

## Data Types

---

### Integer (Bilangan Bulat)

```c
short a = 1;
int b = 50;
long c = 234972389;
long long d = 2394872937401134;
```

---

Berikut merupakan *range* dari masing-masing tipe data integer

Data Type | Range
----------|------------
*short* | -32768 to 32767
*int* | -32768 to 32767
*long* | -2147483648 to 2147483647
*long long* | -(2^63) to (2^63)-1

---

Tipe data integer memiliki versi lain dimana value dari variabel dengan tipe data tersebut bernilai >= 0. Untuk menggunakannya, tambahkan keyword ***unsigned*** di depan tiap tipe data integer.

```c
// Integer
unsigned short a = 1;
unsigned int b = 50;
unsigned long c = 234972389;
unsigned long long d = 2394872937401134;
```

---

Range maksimal tipe data unsigned berukuran dua kali lipat dibandingkan dengan versi integer biasa.

Data Type | Range
----------|------------
*unsigned short* | 0 to 65,535
*unsigned int* | 0 to 65,535
*unsigned long* | 0 to 4,294,967,295
*unsigned long long* | 0 to 18,446,744,073,709,551,615

---

### Decimal (Bilangan Pecahan)

```c
// Decimal (Floating Point)
float e = 3.14;
double f = 17.6342;
long double g = 283.123041034;
long long double h = 123947.1293741293;
```

---

### Character

Tipe data **char** biasa digunakan untuk menyimpan karakter

Berbeda pada bahasa pada umumnya yang memiliki tipe data *string* , bahasa C tidak memiliki tipe data khusus untuk teks. Untuk menyimpan teks, digunakan tipe data char.

```c
// Text
char j = 'f';
char text[] = "Hello";
```

> Tanda [ ] merupakan penanda bahwa variabel tersebut adalah array. Pembahasan lebih dalam terkait array akan ada di slide selanjutnya.

---

### Boolean (Benar atau Salah)

```c
// Boolean
bool k = false;
bool l = true;
```

---

### Const / Literal

Tipe data **const**, atau biasa disebut *literal*, bisa membuat tipe data lain menjadi tidak bisa dirubah (fixed value). Tipe data biasa digunakan untuk mendefinisikan suatu nilai.

```c
// Membuat bilangan bulat menjadi fixed
const int x = 10;

// Mendefinisikan nilai pi
const float pi = 3.14;
```

---

### Array

Array merupakan suatu kumpulan tipe data tertentu pada satu variabel. Untuk membuat array, anda cukup menambahkan tanda **[ ]** pada nama variabel.

Dalam pembuatan array, perlu dispesifikasikan berapa panjang array yang dibutuhkan.

```c
// Inisialisasi array kosong dengan panjang
int kumpulanBilanganBulat[5]; // Menampung 5 value int
char kumpulanKarakter[10];    // Menampung 10 value char
float kumpulanBilanganDesimal[3] // Menampung 3 value float
```

---

Apa yang terjadi jika menginisialisasi array tanpa menspesifikasikan panjang dari array ?

```c
int kumpulanAngka[]; // Error dari kompiler karena tidak menspesifikasikan ukuran/panjang array
```

---

Berikut merupakan visualisasi penggunaan array

```c
char text[] = "Ilkom UNJ";

// Sama saja dengan

char text[9] = {'I','l','k','o','m',' ','U','N','J'};

```

---

Untuk mengakses nilai pada array, dapat digunakan *index* dari value tersebut. Index merupakan nomor urutan value pada array.

```c
// Inisialisasi array dengan value yang ditentukan
int ganjil[5] = {5, 10, 15, 20, 25};

printf("%d", ganjil[0]); // Mencetak index ke-0, yaitu 5
printf("%d", ganjil[3]); // Mencetak index ke-3, yaitu 20
```

---

Apa yang terjadi ketika kamu mencetak index array yang belum diinisialisasi ?

```c
char random[5];
printf("%c", random[2]); // Akan mencetak karakter kosong atau ''
```

---

## Operator Dasar

---

### Assign Operator

Assign operator (' **=** ') digunakan untuk memberikan value pada sebuah variabel.

```c
// Set value pada variabel x
int x = 4;

// Bisa juga digunakan untuk inisialisasi teks
char text[] = "Ini adalah sebuah teks";
```

---

### Mathematical Operator

Mathematical operator ( +, -, \*, /, % ) digunakan untuk melakukan operasi matematika (penjumlahan, pengurangan, perkalian, pembagian, modulo) pada program.

---

```c
int a = 5;
int b = 17;
int c = 4;
int d = 90;
int e = 0;

// Penjumlahan (Sum)
int res = a + b; // 22

// Pengurangan (Minus)
int res = b - c; // 13

// Pembagian (Division)
float res = d / c; // 12.5

// Perkalian (Multiply)
int res = d * e; // 0

// Sisa bagi (modulo)
int res = b % a; // 2

```

---

## Input/Output Library

---

Pada aplikasi *Hello, World!*, terdapat penggunaan library khusus untuk melakukan operasi baca tulis. Library tersebut adalah **stdio.h**.

> Library adalah sekumpulan implementasi untuk mencapai tujuan tertentu pada aplikasi dan menghindari penulisan kode secara berulang. Umumnya suatu *library* memiliki beberapa *function* yang dapat langsung digunakan.

Pada bahasa C, library biasanya didefinisikan dalam bentuk **header file**, yang memiliki extensi *.h*

---

### Mencetak output

Untuk mencetak output ke layar, digunakan ***printf***.

```c
printf("Hello, World!"); // Mencetak Hello, World! ke layar
```

---

### Membaca input dari pengguna

Agar aplikasi bisa menerima input dari pengguna, maka akan digunakan ***scanf***.

```c
int umur;

printf("Masukkan umur kamu : ");
scanf("%d", &umur);

printf("Umur kamu adalah %d tahun!", umur);

```

> Pada contoh scanf, terdapat penggunaan simbol khusus yaitu ***reference*** (&). Untuk saat ini, pastikan untuk menggunakan tanda & ketika ingin menerima input ke variabel **non-char**. Pembahasan tentang reference (dan pointer) akan ada di pertemuan terakhir.

---

### Macam-Macam Format

Pada printf dan scanf, sering kali ditemukan penanda seperti %s, %d, dan lain-lain. Penanda tersebut merupakan format specifier untuk membuat format input dan output.

![bg width:600px right:50%](http://3.bp.blogspot.com/-5b2Smx0fx5E/TrGT3SrXa1I/AAAAAAAAAH4/SsnplVh7agk/s1600/Format+Specifications+in+C+programming+language.bmp)

---

# Thank You
