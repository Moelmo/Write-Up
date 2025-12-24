Prev -> [[Level 18 -> Level 19]]

---

Untuk mendapatkan akses ke tingkat berikutnya, Anda harus menggunakan biner setidiid di dalam homedirectory. Eksekusi tanpa argumen untuk mencari tahu bagaimana untuk menggunakannya. Password untuk tingkat ini dapat ditemukan dalam biasa tempat (/etc/bandit_pass), setelah Anda menggunakan biner yang pasti.

## Bahan Bacaan yang Bermanfaat

[setuid on Wikipedia](https://en.wikipedia.org/wiki/Setuid)

---

# Write Up Level 19

### Level 19

Deskripsi:
	Untuk mengakses level berikutnya, disediakan sebuah **binary setuid** di home directory. Binary tersebut harus dijalankan **tanpa argumen** untuk mengetahui cara penggunaannya. Password level selanjutnya berada di lokasi biasa: `/etc/bandit_pass`.
### Analisis

Pada Linux, **setuid binary** adalah program yang akan berjalan dengan **hak akses pemilik file**, bukan pengguna yang menjalankannya. Artinya, meskipun user biasa tidak memiliki izin membaca file tertentu, **program setuid dapat melakukannya jika pemiliknya memiliki izin tersebut**.

Binary yang disediakan kemungkinan dibuat untuk:

- Menjalankan perintah tertentu
- Dengan hak akses lebih tingg
- Tanpa perlu eksploitasi atau bypass keamanan

---

## Langkah Penyelesaian


1. Masuk ke home direktori dan melihat isi folder 

```bash
ls
```

2. Mengidentifikasi binary setuid dengan melihat permission

```bash
ls -l
```

3. Menjalankan binary **tanpa argumen** sesuai petunjuk soal:

```bash
./bandit20-do
```

4. Membaca outpupt dari program untuk mengetahui fungsi dan cara penggunaannya.

5. Menggunakan binar tersebut sesuai instruksi untuk mengakses file password di `/etc/bandit_pass/bandit20`

```bash
./bandit20-do cat /etc/bandit_pass/bandit20
```

6. Password level berikutnya berhasil diperoleh

### Jawaban(Password)

```
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```

---
Next -> [[Level 20 -> Level 21]]