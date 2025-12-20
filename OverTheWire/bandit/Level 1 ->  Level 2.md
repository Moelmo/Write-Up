Prev → [[Level 0 -> Level 1]]

---
Tingkat Tujuan :
Kata sandi untuk tingkat berikutnya disimpan dalam file yang disebut - yang berlokasi di direktori rumah

## Perintah yang mungkin Anda perlukan untuk menyelesaikan level ini

[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html) , [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html) , [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html) , [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html) , [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html) , [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html)
## Bahan Bacaan yang Bermanfaat

- [Google Cari untuk “Dashed Filename”](https://www.google.com/search?q=dashed+filename)
- [Panduan Bashab-scripting Tingkat Lanjut - Bab 3 - Karakter Khusus](https://linux.die.net/abs-guide/special-chars.html)

## 📁 Apa itu _Dashed Filename_?

**Dashed filename** adalah **nama file yang diawali dengan tanda strip `-`**.

Contoh:

- `-`
- `-file`
- `--test`
- `--spaces in this filename--`

---

## 🤔 Kenapa File Ini Jadi Masalah?

Di Linux:

- Tanda `-` **biasanya dipakai untuk opsi/flag command** 

Contoh:

`ls -a cat -n`

Jadi kalau ada file bernama:

`--file`

Linux akan berpikir:

> “Ini opsi, bukan nama file”

---

## ❌ Contoh Salah

`cat --file`

Bash mengira `--file` itu **opsi**, bukan file.

---

## ✅ Cara Benar Mengakses _Dashed Filename_

### 1️⃣ Pakai path `./` (PALING MUDAH)

`cat ./--file`

Artinya:

> File `--file` yang ada di folder sekarang

---

### 2️⃣ Pakai `--` (Akhiri opsi)

`cat -- --file`

Artinya:

> Setelah ini bukan opsi, tapi nama file

---

### 3️⃣ Digabung dengan spasi (kalau ada spasi)

`cat -- "--spaces in this filename--"`

---

## 🧠 Analogi Sederhana

Bayangkan:

- `-` = tombol perintah
    
- file `-file` = nama anak yang sama dengan tombol
    

Kalau tidak dikasih tanda:

> komputer bingung ini perintah atau nama

---

## 🎯 Kesimpulan Singkat

- **Dashed filename = file yang namanya diawali `-`**
    
- Linux bisa salah paham karena `-` biasanya opsi
    
- Gunakan:
    
    - `./filename`        
    - atau `-- filename`


📌 Ini **trik klasik CTF** dan sering muncul di Bandit 💡


---

# Write Up Level 1

Setelah menyelesaikan Level 0 tadi dan melanjutkan level 1 terlebih dahulu keluar dari akun ssh bandit0, dengan command linux `exit`, setelah itu masuk dengan akun bandit1 sesuai level nya.

## Langkah Penyelesaian

1. Masuk ke server ssh bandit1

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

2. Masukkan password yang telah kita dapatkan di level sebelum nya

```text
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

3. Setelah masuk kita cek di dalalm directory terdapat file apa dengan menggunkan command linux `ls`

output: 

```text
bandit1@bandit:~$ ls
-
```

4. Terdadpat sebuah file di dalam direktory tersebut dengan nama `-` yang dimana kita tidak bisa langsung  membuka menggunakan command linux "`cat -`" jika kita menjalankan command ini di terminal tidak akan terjadi apa apa.

5. Untuk membuka file tersebut kita harus cek  apa saja file tersembunyi menggunakan command linux `du`

```bash
du
```

	output :

```text
bandit1@bandit:~$ du
20	.
```

6. di lihat dari output tersebut terdapat angka 20, angka itu adalah sebuah ukuran file, maka kita coba simpulkan ada sebuah file tersembunyi coba tambahkan "`-a" Artinya menampilan semua file termasuk hidden file

```bash
du -a
```

Output :

```text
bandit1@bandit:~$ du -a
4	./.bash_logout
4	./.bashrc
4	./.profile
4	./-
20	.
```

7. Dan benar, terdapat sebuah file tersembunyi (hidden file) yang diawali dengan tanda titik (`.`). Sesuai soal yang diberikan, petunjuk tersebut disimpan dalam sebuah file bernama `-` yang berlokasi di direktori home. coba kita lihat dengan command linux

```bash
cat ./-
```

Output :

```text
bandit1@bandit:~$ cat ./-
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

## Jawaban (Password)

```text
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

---
Next → [[Level 2 -> Level 3]]