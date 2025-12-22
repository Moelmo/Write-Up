Prev -> [[Level 7 -> Level 8]]

---
Kata sandi untuk tingkat berikutnya disimpan dalam **data** file.**txt** dan satu-satunya baris teks yang terjadi hanya sekali

## Perintah yang mungkin Anda perlukan untuk menyelesaikan level ini

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

> Penjelasan masing masing ada di [[Level 7 -> Level 8]]
## Bahan Bacaan yang Bermanfaat

[Piping and Redirection](https://ryanstutorials.net/linuxtutorial/piping.php)

---

# Write Up Level 8

Di level 8 ini kita diberikan kata sandi yang terdapat di dalam file.txt dan satu-satunya baris teks yang terjadi hanya sekali, ini adalah sebuah clue yang dimana ada banyak baris yang terduplikat  dan hanya ada 1 baris yang tidak berulang atau terduplikat

## Langkah Penyelesaian

1. Masuk ke server SSH bandit8 dengan password yang sudah didapat di level sebelumnya

```bash
ssh bandit8.bandit.labs.overthewire.org -p 2220
```

2. Setelah masuk ke server kita cek di direktori ada apa saja dengan command `ls` , setelah di cek terdapat sebuah file bernama data.txt jika kita cek menggunakan command `cat` maka yang muncul teks yang tidak beraturan.

3.  Untuk mengetahui kata sandi yang berada di dalam `data.txt` kita pakai command bernama `sort` dan `uniq` fungsi kedua command ini yang pertama `sort` berfungsi untuk mengurutkan abjad dari A-Z dan uniq untuk mengecek ada berapa kata yang terduplikat atau diulangi dalam 1 file.

```bash
sort data.txt | uniq -u
```

4. Setelah kita eksekusi command nya akan muncul output berupa kata sandi untuk level berikutnya, `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`

## Jawaban(Password)

```
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```


---

Next -> [[Level 9 -> Level 10]]