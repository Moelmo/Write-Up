Prev -> [[Level 4 -> Level 5]]

---

Kata sandi untuk tingkat berikutnya disimpan dalam file di suatu tempat di bawahnya di **inhere** direktori dan memiliki semua properti berikut:

- human-readable
- 1033 bytes in size
- not executable

---

# Write Up Level 5

Seperti di level sebelumnya untuk masuk ke level 5 kita harus dapatkan password di level sebelumnya, nah di level  5 ini sudah mulai berbeda dengan level sebelumnya yang dimana level sebelumnya di kasih petunjuk hanya berupa nama folder yang isinya password, di level 5 ini kita di berikan sebuah clue yaitu ada 3 sebagai berikut

- human-readable  -> yang bisa di baca oleh manusia
- 1033 byte in size -> ukuran tepat 1033 byte 
- not executable -> sebuah file yang tidak bisa di eksekusi hanya bisa di baca

## Langkah penyelesaian

1. Login ke bandit5 menggunakan ssh server

```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
```

2. cek direktori awal dengan command `ls`

3. terdapat sebuah folder `inhere`, langsung saja masuk ke dalam folder tersebut dengan command `cd`

4. setelah masuk cek isi folder tersebut, terdapat banyak direktori dan di dalam direktori itu terdapat banyak file

5. untuk mencari password ke level selanjutnya kita harus mencari password itu di salah satu file tersebut, tetapi tidak mungkin kita cek satu per satu.

6. disinilah clue itu di pakai, kita coba cari sebuah file dengan command `find` dan kita samakan dengan clue

Tambahin setelah command `find`:

> Perintah ini digunakan untuk mencari file biasa (`-type f`) dengan ukuran tepat 1033 byte (`-size 1033c`) dan tidak memiliki izin eksekusi (`! -executable`)

```bash
find . -type f -size 1033c ! -executable
```

7. Output nya akan menunjukkan ke direktori file yang bernama `./maybehere07/.file2`, langsung saja cek file tersebut dengan command `cat`

## Jawaban (password)

```
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

---

Next -> [[Level 6 -> Level 7]]