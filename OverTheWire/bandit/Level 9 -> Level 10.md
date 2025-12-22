Prev -> [[Level 8 -> Level 9]]

---

Kata sandi untuk tingkat berikutnya disimpan dalam **data** file.**txt** dalam salah satu dari beberapa string yang dapat dibaca manusia, didahului oleh beberapa '=' karakter.

---

# Write Up Level 9

Kita diberi sebuah soal yang mengharuskan kita mencari kata sandi didalam sebuah data file.txt dalam satu dari beberapa string yang dapat di baca manusia. didahului oleh beberapa `"="` karakter.  

## Langkah Penyelesaian

1. Masuk ke server SSH bandit9 dengan password yang didapat di level sebelumnya

```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```

2. setelah masuk ke dalam server kita cek isi direktori menggunakan command `ls`, di dalam direktori terdapat sebuah file bernama `data.txt`  jika kita cek file tersebut akan muncul sebuah teks yang tidak bisa di baca oleh manusia.

3. untuk mengetahui isi password didalam file tersebut yang tidak bisa dibaca oleh manusia, terdapat sebuah clue di soal yaitu sebuah kata sandi didahului karakter `"="` maka kita akan mengecek `data.txt` menggunakan command `strings` dan kita ambil kata kunci `"="` untuk melihat kata sandi yang disembunyikan.

```bash
strings data.txt | grep "="
```

4. maka output akan menampilkan semua string yang ada karakter `"="` dan password nya adalah `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`

## Jawaban(Password)

```
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```


---

Next ->[[Level 10 -> Level 11]]
