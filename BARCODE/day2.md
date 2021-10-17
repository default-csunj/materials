---
ttle: BARCODE
author: DEFAULT UNJ
date: 2021-08-22
---

# BARCODE

## Day - 2

---

Selamat datang di pertemuan kedua BARCODE. Pada sesi kali ini kalian akan belajar beberapa hal:

- Kondisional
- Looping / Perulangan
- Function

Selamat mengikuti !

---

## Conditional

---

Dalam membuat sebuah program, sering terjadi situasi dimana kita perlu memberikan kontrol terhadap bagaimana program berjalan. Sebagai contoh, apabila kita ingin membandingkan umur dari dua orang berbeda, maka kita perlu membandingkan dua variabel. Pada bagian ini anda akan mempelajari tentang membuat *control flow* untuk suatu program.

---

### Conditional Statement (if ... else if ... else)

```c
if (kondisi1){
  // Blok ini dijalankan jika kondisi1 bernilai true
  ...
} else if (kondisi2){
  // Blok ini dijalankan jika kondisi2 bernilai true
  ...
} else {
  // Blok ini dijalankan jika kondisi1 dan kondisi2
  // tidak memenuhi
  ...
}
```

---

### Logical Operator

Logical operator digunakan untuk melakukan operasi logika. Operator ini biasa digunakan untuk tipe data *boolean*, tetapi juga bisa dikombinasikan dengan hasil perbandingan dari operator relasional. Terdapat tiga operator logika yang umum digunakan pada C, yaitu **AND** (&&), **OR** (||), dan **NOT** (!).

---

```c
int a = true;
int b = false;

// a && b -> false
// a || b -> true
//   !a   -> false
```

---

### Contoh Case Conditional/Logical

```c
int umurBudi = 17;
int umurAndi = 21;

if ((umurBudi >= 18 && umurAndi >= 18) == true) {
  printf("Budi dan Andi sudah dewasa, boleh punya SIM")
}

// Bedakan dengan ini

if ((umurBudi >= 18 || umurAndi >=) == true) {
  printf("Salah satu dari Budi atau Andi sudah dewasa")
}
```

---

### Truth Table

![bg width:700px right:65%](https://merriam-webster.com/assets/mw/static/table/collegiate/truthtab.jpg)
Berikut merupakan tabel kebenaran yang menggambarkan hasil dari masing-masing statement.

---

### Relational Operator

Relational operator ( **>** , **<** , **==** ) digunakan untuk membandingkan dua variabel

```c
int a = 7;
int b = 10;

if (a > b){
  printf("a lebih tua dari b\n");
} else if (a < b){
  printf("a lebih muda dari b\n");
}else if (a == b){
  printf("a dan b seumuran\n");
}
```

---

## Looping

---

Dalam programming, looping adalah serangkaian kode yang di eksekusi berulang kali, dan berhenti jika telah memenuhi suatu kondisi tertentu.

Pada umumnya, ada dua jenis looping yang sering digunakan, yaitu **for-loop** dan **while-loop**.

---

### Sekilas tentang Looping

Untuk mengetahui kapan looping harus berhenti, digunakan sebuah variabel yang nilainya dicek setiap satu loop.

Apabila looping tidak mengecek variabel, atau variabel tersebut tidak pernah mencapai kondisi untuk berhenti, maka akan terjadi **infinite loop** (program tidak akan berhenti).

---

### For-Loop

Berikut merupakan struktur for-loop pada C

```c
for (<inisialisasi_variabel>; <kondisi>; <perubahan_variabel>){
  ...
}
```

Contoh

```c
for (int i = 0; i < 10; i++){
  // Mencetak angka dari 0 - 9
  printf("Looping ke %d\n", i);
}
```

---

### While-Loop

Terdapat dua jenis while-loop, yaitu *while-do* dan *do-while*. Berikut merupakan struktur while-loop pada C

```c
while(<kondisi>){
  ...
}

do {
  ...
}while(<kondisi>)
```

Lalu apa perbedaannya ? Pada *while-do*, variabel dicek ketika memulai looping. Sementara pada do while, variabel dicek setelah menjalankan blok kode.

Perhatikan bahwa pada while-loop, tidak ada pengubah variabel. Perubahan variable dilakukan didalam blok kode.

---

### Keyword *break* dan *continue*

Terkadang, kita ingin mengintervensi jalannya looping pada situasi tertentu. Untuk hal ini, terdapat dua keyword khusus yang dapat digunakan, yaitu **break** dan **continue**.

Keyword break digunakan untuk memaksa looping untuk berhenti. Sementara keyword continue digunakan untuk mengabaikan kode lain dan melakukan perulangan selanjutnya.

---

```c
for(int i = 1; i < 10; i++){
  if (i % 2 == 0){
    continue;
  }

  printf("%d\n", i);
}
```

```c
int j = 10;
while(j >= 1){
  if (j == 5){
    break;
  }
  printf("Nilai j adalah %d\n", j);
}
```

---

## Function

---

*Function* merupakan blok kode yang hanya dijalankan ketika dipanggil. Seperti fungsi pada matematika, *function* pada bahasa pemrograman memiliki parameter sebagai nilai input bagi fungsi tersebut. Sintaks *function* pada C pada umumnya terlihat seperti berikut:

```c
double triangle_area(double width, double height){
  double result = 0.5 * width * height;

  return result;
}
```

---

### Parameter

Parameter digunakan sebagai nilai input bagi sebuah fungsi. Format dari parameter adalah **<tipe_data> <nama_variabel>**. Sebuah fungsi dapat diinputkan beberapa parameter sekaligus.

```c
/*                    Parameter       Parameter
                          🠗               🠗
*/
double triangle_area(double width, double height){
  ...
```

> C menggunakan konsep *pass by value* untuk parameter fungsi, yang artinya adalah variabel yang digunakan sebagai parameter hanya akan diambil value nya saja oleh fungsi.

---

### Return Value

Return value merupakan nilai kembalian dari sebuah fungsi. Fungsi bisa mengembalikan nilai berupa tipe data apa saja, atau tidak mengembalikan nilai sama sekali (dengan tipe data ***void***)

```c
// Return value
// 🠗
double triangle_area(double width, double height){
  ...
  // Return variable
  //        🠗
  return result;
}
```

---

### Contoh Function

```c
bool function2(int number){
  if (number % 2 == 0){
    return true;
  }else{
    return false;
  }
}
```

---

# Thank You
