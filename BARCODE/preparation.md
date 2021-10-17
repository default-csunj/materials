---
title: BARCODE
author: DEFAULT UNJ
date: 2021-07-05
footer: '![height:60px](./assets/logo_banner_black.png)'
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

---

Selamat datang di kelas **BARCODE**. Kelas ini bertujuan untuk mengenalkan peserta tentang bagaimana membuat suatu program.

Di **BARCODE**, anda akan diajarkan berbagai hal dasar yang biasanya ada pada setiap program. Selamat mengikuti !

---

Presentasi ini akan mencakup hal-hal yang anda perlu siapkan untuk mengikuti kelas **BARCODE**. Apabila terdapat kendala ketika mengikuti langkah-langkah yang ada, jangan sungkan untuk bertanya kepada teman atau mentor ya.

---

# Instalasi Tools

---

Untuk membuat suatu program, diperlukan dua hal dasar yaitu:

- **Kode program** (*source code*) yang merupakan rancangan dari program yang akan dibuat
- **Compiler/interpreter** untuk menterjemahkan bahasa program yang telah tulis kedalam bahasa mesin, untuk kemudian dijalankan

Pada BARCODE, bahasa pemrograman yang akan digunakan adalah **C++**. Pada bagian selanjutnya, akan dijelaskan langkah untuk menyiapkan perangkat anda untuk membuat program C++.

---

## Compiler

---

### Windows

Compiler GCC dapat diunduh melalui tautan berikut:

[https://github.com/jmeubank/tdm-gcc/releases/download/v10.3.0-tdm64-2/tdm64-gcc-10.3.0-2.exe](https://github.com/jmeubank/tdm-gcc/releases/download/v10.3.0-tdm64-2/tdm64-gcc-10.3.0-2.exe)

TODO: installation step (daffa)

---

### macOS

Pastikan bahwa pada perangkat kamu telah terinstall *package manager* **Homebrew**

```bash
brew install gcc
```

---

### Linux

Pada sistem operasi Linux, cukup menggunakan *package manager* dari masing-masing distro dan install package **gcc**.

```bash
# Debian/Ubuntu
sudo apt install gcc

# Fedora
sudo dnf install gcc

# Arch/Manjaro
sudo pacman -Sy gcc
```

---

## Code Editor

---

Terdapat banyak pilihan *code editor* yang dapat anda gunakan. Anda bebas untuk memilih code editor kesukaan anda. Untuk saat ini, sebagai contoh akan digunakan adalah **Visual Studio Code**.

Visual Studio Code dapat diunduh melalui tautan berikut:
[https://code.visualstudio.com/download](https://code.visualstudio.com/download)

> Selain code editor, terdapat opsi yang menyediakan *tools* lebih lengkap, yaitu *Integrated Development Environment (IDE)*. Contoh IDE yang populer untuk C++ antara lain adalah CLion dan Visual Studio.

---

Pada materi kali ini anda telah belajar untuk menyiapkan *development environment* yang akan digunakan untuk membuat program, yaitu compiler dan code editor. Pada pertemuan selanjutnya, akan diajarkan dasar-dasar bahasa C++

Sampai jumpa di pertemuan selanjutnya !
