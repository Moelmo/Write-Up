Prev -> [[Level 10 -> Level 11]]

---

Kata sandi untuk tingkat berikutnya disimpan dalam data **file.txt**, di mana semua huruf kecil (a-z) dan huruf besar (A-Z) telah dirotasi oleh 13 posisi

## Bahan Bacaan yang Bermanfaat

[Rot13 on Wikipedia](https://en.wikipedia.org/wiki/ROT13)

**ROT13** adalah **cara sederhana untuk menyamarkan teks** dengan **menggeser setiap huruf 13 langkah** di alfabet.

🔹 A → N  
🔹 B → O  
🔹 N → A

📌 Ciri penting:

- Hanya berlaku untuk **huruf**
- **Bukan enkripsi kuat**
- Di-decode dengan cara **yang sama**

Contoh:

```
HELLO → URYYB
```
---


# Write Up Level 11

Di level 11 ini kita mencari sebuah kata sandi yang disimpan di dalam data file.txt, dimana semua huruf kecil (a-z) dan huruf besar (A-Z) telah di rotasi 13 posisi.

## Langkah Penyelesaian

1. Masuk ke server SSH bandit11 dan masukkan password yang didapat di level sebelumnya.

```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```


2. setelah masuk kita cek direktori dengan command `ls`, di direktori terdapat file data.txt, kita cek dan terlihat isinya yang sudah di-encode, sesuai clue yang berada di soal huruf telah di rotasi 13 posisi yang dimana kita harus meng decode dengan ROT13, menggunakan command `tr`

```bash
cat data.txt | tr A-Za-z N-ZA-Mn-za-m
```

 > Perintah `tr` digunakan untuk menukar karakter satu per satu sesuai pola yang ditentukan.

3. setelah kita decode muncul output `The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4` , ini adalah password untuk lanjut ke level berikutnya

## Jawaban(Password)

```
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```
 
---

Next -> [[Level 12 -> Level 13]]