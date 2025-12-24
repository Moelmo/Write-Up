Prev -> [[Level 16 -> Level 17]]

---

Ada 2 file di direktori Home: **passwords.old dan passwords.new.** Password untuk tingkat berikutnya adalah di **passwords.new** dan merupakan satu-satunya baris yang telah diubah antara **passwords.old dan passwords.new**

**CATATAN: jika Anda telah memecahkan level ini dan melihat ‘Byebye!’ ketika mencoba untuk masuk ke bandit18, ini terkait dengan tingkat berikutnya, bandit19**

## Perintah yang mungkin Anda perlukan untuk menyelesaikan level ini

cat, grep, ls, diff

## 🔁 `diff`

**Fungsi:** Membandingkan dua file  
**Contoh:**

```bash
diff file1.txt file2.txt
```

---

# Write Up

### Level 17

Deskripsi:
	kita diberikan 2 file di direktori Home yaitu passwords.old dan passwords.new. Password untuk lanjut ke Level berikutnya adalah di Password.new dan merupakan satu-satunya baris yang telah diubah antara passwords.old dan passwords.new.


### Analisis

Kita diberikan sebuah soal yang dimana ada 2 file passwords.new dan passwords.old, kata sandi untuk lanjut di level berikutny ada di passwords.new dan merupakan satu baris yang telah di ubah diantara password.old dan password.new, jadi kita akan membandingkan passwords.new dan passwords.old untuk mencari 1 baris yang berubah.


### Langkah Penyelesaian

1. Masuk ke server bandit17 menggunakan private key yang di dapat di level sebelumnya

2. cek isi direktori home menggunakan command `ls`, terdapat 2 file yaitu passwords.new dan passwords.old, langsung saja bandingkan kedua file tersebut untut melihat satu baris yang berubah, menggunakaan commnad `diff`

```bash
diff passowrds.new passwords.old
```

Output: 

```text
42c42
< x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
---
> pGozC8kOHLkBMOaL0ICPvLV1IjQ5F1VA
```

3. Output menunjukkan 1 baris yang berubah di kedua file tersebut yang artinya kita membandingkan file passwords.new dengan passwords.old, passwords.new berisi `x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO` dan passwords.old berisi `pGozC8kOHLkBMOaL0ICPvLV1IjQ5F1VA`.

### Jawaban(Password)

Setelah membandingkan kedua file tersebut kita akan diberikan password yang benar

```
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```

---

Next -> [[Level 18 -> Level 19]]