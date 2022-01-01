---
title: BARCODE
author: DEFAULT UNJ
date: 2021-07-05
footer: '![height:60px](./assets/logo_banner_black.png)'
<!-- class: invert -->
---
<style>
section {
  backgroundColor: #AAAAAA;
  font-family: 'JetBrains Mono';
  text-align: justify;
}
footer {
  right: 30px;
  text-align: right;
}
h2, h3 {
    font-weight: bolder;
}
img[alt~="center"] {
  display: block;
  margin: 0 auto;
}
</style>

# BARCODE

## Day 3

---

Selamat datang di pertemuan keempat BARCODE. Sesi pembelajaran kali ini akan sedikit berbeda dibanding sesi sebelumnya. Topik pembahasan sesi kali ini akan berfokus tentang macam-macam algoritma dan penerapannya.

Selamat mengikuti !

---

## Algoritma Rekursif

---

Kata rekursif sendiri merupakan suatu metode untuk menyelesaikan masalah dengan memecah suatu masalah menjadi lebih kecil.

> Dalam penerapannya pada programming, rekursif diterapkan melalui suatu fungsi tertentu yang nantinya akan memanggil fungsi itu sendiri

Terdapat dua bagian dari fungsi rekursif:

- Base Condition (Sebuah kondisi untuk menentukan jalannya fungsi rekursif. Jika mereturn True, maka fungsi berhenti dan Jika mereturn False maka akan dilanjutkan dengan Case Recursive)
- Case Recursive (Sebuah Case jika Base Condition blm terpenuhi yang berjalan sampai Base Condition terpenuhi)

Mungkin cukup membingungkan ? Mari menuju contoh *usecase*

---

### Fungsi Faktorial

Masalah faktorial merupakan salah satu masalah yang dapat diselesaikan dengan pendekatan rekursif. Dalam menggunakan pendekatan rekursif, hal pertama yang perlu kita cari adalah **base case** dari masalah tersebut.

---

Untuk menentukan base case, kita bisa memulai dengan menggunakan contoh kasus yang kecil. Mari kita coba dengan menggunakan nilai dari **3!**

```sh
3! = 3 * 2 * 1
```

Dari case diatas, terdapat suatu pola khusus, yaitu

```sh
3! = 3 * (3-1) * (3-2)
```

Atau jika digeneralisir dapat menjadi

```sh
n! = n * (n-1) * (n-2)
```

---

Seperti aturan umum yang kita ketahui, fungsi faktorial akan mengalikan hingga nilainya 1, dengan pengecualian untuk **0! = 1**. Oleh karena itu, dapat ditemukan base case sebagai berikut

```sh
n! = n * (n-1) * (n-2) * ... * 1, dengan kondisional 0! = 1
```

---

Untuk menentukan base case, langkah-langkah yang harus dilakukan adalah **menginisialisasi masalah / algoritma**

Disini bisa dibilang kita diharuskan untuk menentukan best case dan worst case dari suatu masalah tersebut, seperti contoh dalam faktorial. Faktorial memiliki best case yaitu ketika sudah menemukan angka satu dan worst case yaitu ketika menemukan angka <= 0. Ketika sudah ditentukan best case dan worst case nya, maka untuk membuat fungsi rekursif menjadi lebih mudah.

---

![bg width:600px right:50%](./assets/rekursif.jpg)

```c
// Mencari nilai dari n faktorial
int faktorial(int n){
  // Pengecualian pada 0!
  if (n == 0)
    return 1;

  return n * faktorial(n-1);
}

int main(){
  int input = 4;
  int hasil = faktorial(input);
  printf(
    "%d! adalah %d",
    input,
    hasil
  );
}
```

---

### Bilangan Fibonacci

Bilangan fibonacci / *fibonacci sequence* merupakan set bilangan seperti berikut

0, 1, 1, 2, 3, 5, ... dengan catatan **F0 = 0, dan F1 = 1**

---

Mari kita coba dengan angka yang kecil yaitu bilangan fibonnaci ke-0 dan ke-1 yaitu

```sh
F(0) = 0
F(1) = 1
```sh

dan untuk bilangan-bilangan setelahnya dapat di definisikan sebagai

```sh
F(2) = F(0) + F(1) = 1 + 0 = 1
F(3) = F(1) + F(2) = 1 + 1 = 2
F(4) = F(2) + F(3) = 1 + 2 = 3
```

dari perhitungan diatas dapat digeneralisir menjadi

```sh
F(n) = F(n-1) + F(n-2)
```

Dengan pengecualian F(0) dikarenakan

```sh
F(0) = F(-1) + F(-2)
```

---

Maka, *Base case* dari masalah ini adalah : **Fn = F(n-1) + F(n-2)**, dimana n adalah urutan bilangan fibonacci yang kita inginkan dengah kondisional n != 0 (ketika n = 0 rekursif berhenti)

---

```c
// Mencari bilangan fibonacci ke-n
int fibonacci(int n){
  // Bilangan urutan ke-0
  if(n ==  0)
    return 0;

  // Bilangan urutan ke-1
  if(n == 1)
    return 1;

  return fibonacci(n-1) + fibonacci(n-2);
}

int main() {
  int input = 7;
  int hasil = fibonacci(input);
  printf("Fibonacci ke-%d : %d", input, hasil);
}
```

---

### Pertanyaan Seputar Rekursif

**Q: Kenapa perlu menggunakan rekursif ? Bukannya solusi bisa dicapai dengan iterasi seperti for loop atau while loop juga?**
**A:** Pada realitanya, apabila suatu masalah bisa diselesaikan dengan iterasi, maka juga bisa diselesaikan dengan rekursif. Hanya saja, pada beberapa kasus tertentu, pendekatan rekursif membuat penulisan program lebih mudah. Sebagai contoh, struktur data *tree* lebih mudah diimplementasikan dengan rekursif dibandingkan dengan iterasi.

---

### Catatan Penting Tentang Rekursif

Perlu diperhatikan bahwa dalam penerapan pendekatan secara rekursif, seringkali ditemukan masalah yaitu penggunaan memori yang terlalu banyak. Pendekatan rekursif biasa melakukan pemanggilan suatu fungsi secara berulang hingga parameter dari fungsi tersebut sudah memenuhi kriteria tertentu.

Pemanggilan fungsi sendiri membuat sistem operasi **mengalokasikan memori baru setiap terpanggilnya suatu fungsi** (dan juga isi fungsi jika ada, seperti variabel lokal dan lain-lain), berbeda dengan iterasi yang hanya **memperbarui nilai dari variabel** yang sudah ada (*memoization*) .

---

## Algoritma Pengurutan / Sorting

---

Algoritma *sorting* digunakan dalam berbagai situasi. Algoritma sorting juga memiliki banyak variasi, yang masing-masing memiliki keunggulan dibanding yang lainnya dalam beberapa aspek (kecepatan, penggunaan memori). Untuk memahami algoritma sorting, cara terbaik adalah dengan memahami konsepnya terlebih dahulu.

---

### Insertion Sort

*Insertion sort* merupakan salah satu algoritma sorting yang mudah untuk dipahami.

Metode yang digunakan dalam *Insertion sort* adalah dengan membandingkan dan mengurutkan antara 2 data pertama pada array, kemudian membandingkan apakah data pada array selanjutnya sudah berada di tempat yang semestinya

---

### Penggambaran Insertion Sort

![Insertion Sort](https://www.section.io/engineering-education/sorting-algorithms-in-js/insertion-sort.png)

---

### Penjelasan

- Iterasi Pertama
  - Inisialisasi
- Iteriasi kedua
  - 23 > 1 maka, ditukar
- Iterasi ketiga
  - 23 > 10, maka ditukar
- Iterasi keempat
  - 23 > 5, maka ditukar
  - 10 > 5, maka ditukar
- Iterasi kelima
  - 23 > 2, maka ditukar
  - 10 > 2, maka ditukar
  - 5 > 2, maka ditukar
- Selesai

---

### Code untuk Insertion Sort

```c
#include <stdio.h>

// function untuk menjalankan insertion sort
static void insertionsort(int Array[], int n) {
  for(int i=0; i<n; i++) {
    int curr = Array[i];
    int j = i - 1;
    while(j >= 0 && curr < Array[j]) {
      Array[j + 1] = Array[j];
      Array[j] = curr;
      j = j - 1;
    }
  }
}

```

---

# Terima Kasih
