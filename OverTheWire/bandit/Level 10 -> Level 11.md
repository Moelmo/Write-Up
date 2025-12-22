Prev -> [[Level 9 -> Level 10]]

---

Kata sandi untuk tingkat berikutnya disimpan dalam data **file.txt**, yang berisi data yang dikodekan base64

## Perintah yang mungkin Anda perlukan untuk menyelesaikan level ini

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd
## Bahan Bacaan yang Bermanfaat

[Base64 on Wikipedia](https://en.wikipedia.org/wiki/Base64)

**Base64** adalah **encoding** untuk mengubah data menjadi teks aman dibaca/dikirim.  
✔ Bukan enkripsi  
✔ Bisa di-decode balik  
✔ Sering dipakai di CTF & web

Contoh:

```bash
echo halo | base64
```


---

# Write Up Level 10

Di level 10 ini kita diberikan sebuah soal untuk mencari kata sandi dalam data file.txt, yang berisi data yang dikodekan base64.

## Langkah Penyelesaian

1. Masuk ke server SSH bandit10 .

```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
```

2. Setelah masuk ke server kita cek direktori seperti biasa dengan command `ls`, di direktori terdapat sebuah file bernama `data.txt`, jika kita cek file tersebut menggunkan `cat`  maka yang muncul adalah teks yang tidak beraturan.

Output:
```text
VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==
```

3. Untuk mengetahui kata sandi yang berada dalam `data.txt` yang sudah di encoding, pertama kita cek jenis encoding nya, dalam soal terdapat sebuah clue yang dimana file tersebut dikodekan base64, maka encoding yang di pakai adalah base64, ciri-ciri encoding ini adalah akhir teks akan ada karakter `"==`" , untuk melakukan decode encoding ini kita pakai command `base64 -d` yang dimana arti `-d` itu adalah decode.

```bash
base64 -d data.txt
```

4. maka output  nya menghasilkan teks yang sudah di decode `The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr` yang isinya adalah berupa kata sandi.

> “Base64 digunakan untuk mengubah data biner menjadi teks agar mudah dikirim.”
## Jawaban(Password)

```
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

---

Next -> 