Prev → [[Level 1 ->  Level 2]]

---
Kata sandi untuk tingkat berikutnya disimpan dalam file yang disebut `--spaces in this filename--`yang berlokasi di direktori Home

## Perintah yang mungkin Anda perlukan untuk menyelesaikan level ini

[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html) , [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html) , [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html) , [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html) , [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html) , [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html)

## Bahan Bacaan yang Bermanfaat

- [Google Cari “Spaces in filename”](https://www.google.com/search?q=spaces+in+filename)


---

## 📁 Apa itu _Spaces in Filename_?

**Spaces in filename** artinya **nama file yang punya spasi (jarak)** di dalamnya.

### Contoh:

`file saya.txt bandit level 1.md`

---

## ❗ Kenapa Spasi di Nama File Bermasalah?

Bash (terminal Linux) **menganggap spasi sebagai pemisah perintah**.

Jadi Bash mikir:

`cat file saya.txt`

Artinya:

- `file`
- `saya.txt`

➡️ Padahal itu **satu file**, bukan dua.

---

## ✅ Cara Mengatasi File dengan Spasi

### 1️⃣ Pakai tanda petik `" "` (PALING UMUM)

`cat "file saya.txt"`

---

### 2️⃣ Pakai backslash `\`

`cat file\ saya.txt`

---

### 3️⃣ Hindari dari awal (BEST PRACTICE)

Gunakan **dashed filename** 👇

`file-saya.txt`

---

## 🧠 Contoh Kesalahan Umum

❌ Salah:

`rm file saya.txt`

✔️ Benar:

`rm "file saya.txt"`

atau:

`rm file\ saya.txt`

---

## 🐧 Kenapa Programmer & Hacker Menghindari Spasi?

- Ribet diketik
- Mudah error
- Bikin script gagal
- Susah di-automation

---

## ⭐ Solusi Paling Aman

**Jangan pakai spasi sama sekali.**  
Ganti dengan:

- `-` (dashed filename)
- `_` (underscore)

Contoh:

`bandit-level-1.md bandit_level_1.md`

---

## 🎯 Kesimpulan

- Spasi bikin Bash bingung
- Bisa diakali pakai `" "` atau `\`
- **Paling aman: jangan pakai spasi**

sumber : ChatGPT

---


# Write Up Level 2

Setelah menyelesaikan Level 1, pada Level 2 kita kembali login ke server SSH menggunakan akun **bandit2** dan password yang telah didapatkan dari level sebelumnya.

## Langkah Penyelesaian

1. Masuk ke server SSH bandit2

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

Setelah itu, masukkan password yang diperoleh dari Level 1.

2. Mengecek isi direktori home

Untuk mengetahui file apa saja yang ada di dalam direktori home, gunakan  command Linux `ls`.

```bash
ls
```

Output:

```text
bandit2@bandit:~$ ls --spaces in this filename--
```


 3. Analisis Masalah

Terlihat terdapat sebuah file dengan nama  
`--spaces in this filename--`.

File ini **tidak dapat dibuka secara langsung** karena:

- Namanya **diawali dengan tanda strip (`--`)**
- Mengandung **spasi**
- Bash mengira nama tersebut sebagai **opsi command**

Jika langsung menggunakan:

```bash
cat "--spaces in this filename--"
```

Maka akan muncul error:

```text
cat: unrecognized option '--spaces in this filename--' Try cat --help' for more information.
```

 4. Solusi Membuka File

Untuk memberitahu Bash bahwa ini adalah **nama file, bukan opsi**, kita dapat menggunakan salah satu cara berikut:

- Menambahkan `./` di depan nama file
- Menggunakan `--` untuk menghentikan parsing opsi

Pada level ini digunakan cara pertama.

```bash
cat "./--spaces in this filename--"
```

Output:

```text
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```

## Jawaban (Password)

```text
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```

Next -> [[Level 3 -> Level 4]]