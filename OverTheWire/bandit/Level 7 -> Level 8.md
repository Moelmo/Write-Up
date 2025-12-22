Prev -> [[Level 6 -> Level 7]]

---

Kata sandi untuk tingkat berikutnya disimpan dalam **data** file.**txt** di samping kata **sejuta**

## Perintah yang mungkin Anda perlukan untuk menyelesaikan level ini

[man](https://manpages.ubuntu.com/manpages/noble/man1/man.1.html), grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

## 🔍 `grep`

**Fungsi:** Mencari baris yang mengandung pola tertentu di file atau output command lain.

`grep "keyword" file.txt`

Digunakan untuk filtering data teks secara cepat.

---

## 📏 `sort`

**Fungsi:** Mengurutkan baris teks secara alfabetis atau numerik.

`sort data.txt`

Sering dipakai sebelum `uniq`.

---

## 👯 `uniq`

**Fungsi:** Menghilangkan atau mendeteksi baris duplikat.

`uniq -u`

⚠️ Harus didahului `sort` agar bekerja dengan benar.

---

## 🔎 `strings`

**Fungsi:** Mengekstrak string ASCII yang dapat dibaca manusia dari file biner.

`strings file.bin`

Umum dipakai pada analisis file biner CTF.

---

## 🔐 `base64`

**Fungsi:** Encode dan decode data dalam format Base64.

`base64 -d`

Bukan enkripsi, hanya encoding.

---

## 🔄 `tr`

**Fungsi:** Melakukan translasi atau substitusi karakter.

`tr 'A-Z' 'a-z'`

Sering dipakai untuk ROT, case conversion, atau sanitasi teks.

---

## 📦 `tar`

**Fungsi:** Mengarsipkan banyak file atau direktori menjadi satu file.

`tar -xvf file.tar`

Digunakan untuk ekstraksi atau pembuatan arsip.

---

## 🗜️ `gzip`

**Fungsi:** Kompresi dan dekompresi file dengan format `.gz`.

`gunzip file.gz`

---

## 🗜️ `bzip2`

**Fungsi:** Kompresi alternatif dengan rasio lebih tinggi dibanding gzip.

`bunzip2 file.bz2`

---

## 🧬 `xxd`

**Fungsi:** Menampilkan isi file dalam format hexadecimal (hex dump).

`xxd file`

Digunakan untuk inspeksi low-level data.

---

## 🧠 Ringkasan Teknis

|Tool|Peran Utama|
|---|---|
|`grep`|Filter teks|
|`sort`|Urutkan data|
|`uniq`|Deteksi duplikat|
|`strings`|Ekstrak ASCII|
|`base64`|Encode / decode|
|`tr`|Transform karakter|
|`tar`|Arsip|
|`gzip`|Kompresi|
|`bzip2`|Kompresi|
|`xxd`|Analisis hex|

---

# Write Up Level 7

Di level ini kita diberikan sebuah data berbentuk file.txt, dan terdapat kata sandi, di samping kata sandi ada kata kunci "millionth".

## Langkah Penyelesaian

1. Masuk ke server SSH bandit7 dengan password yang sudah di dapat di level sebelumnya

```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
```

2. Setelah masuk ke server bandit7 kita cek apa yang ada di dalam direktori dengan command `ls`, setelah di cek terdapat sebuah file bernama `data.txt`, sandi berada di dalam file tersebut dengan kata kunci huruf "millionth"

3. setelah mendapatkan file dan clue dengan kata kunci huruf "millionth" langsung saja kita ambil kata kunci itu yang berada di dalam file data.txt dengan manggunakan command `grep`

>  Perirntah `grep` di gunakan untuk

```bash
grep "millionth" data.txt
```

Output:

```text
millionth	dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

## Jawaban (Password)

```
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

---

Next -> [[Level 8 -> Level 9]]