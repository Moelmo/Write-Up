Prev -> [[Level 12 -> Level 13]]

---
Kata sandi untuk tingkat berikutnya disimpan di **/etc/bandit_pass/bandit14 dan hanya dapat dibaca oleh pengguna bandit14.** Untuk level ini, Anda tidak mendapatkan kata sandi berikutnya, tetapi Anda Dapatkan kunci SSH pribadi yang dapat digunakan untuk masuk ke tingkat berikutnya. Lihatlah perintah yang membawa Anda ke tingkat bandit sebelumnya, dan cari tahu cara menggunakan kunci untuk level ini.

---

# Write Up Level 13

### Level 13

Deskripsi :
Kata sandi untuk lanjut ke tingkat berikutnya tersimpan di `/etc/bandit_pass/bandit14` dan hanya dapat dibaca oleh pengguna bandit14. Untuk level ini, anda tidak mendapatkan katasandi berikutnya, tetapi anda mendapatkan SSH Key Private yang dapat digunakan untuk masuk ke tingkat berikutnya. 

### Analisis

Dari soal yang diberikan kita dikasih sebuah kunci untuk masuk ke server bandit14 maka yang kitabutuhkan adalah mendapatkan kunci itu dan untuk terhubung ke bandit14 melalui private key kita menggunakan command `scp -P <port> <user>:<file> <file disimpan>`untuk mengunduh file yang berada di bandit13 ke komputer kita.

### Langkah Penyelesaian

1. Masuk ke server bandit13

```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
```

2. setelah masuk ke server cek isi direktori, terdapat file bernama `sshkey.private` cek ekstensi file tersebut, ekstensi yang di pakai adalah `PEM RSA private key` yang berarti itu adalah kunci untuk masuk ke server bandit14.

3. keluar dari bandit13 lalu gunakan command `scp` untuk mendownload filenya, setelah mendownload file nya langsung masuk ke server bandit14 dengan manggunakan command `ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220`.

4. Setelah mencoba masuk ternyata file tersebut permission nya masih 0640 yang seharuhnya 600 maka kita  ubah permission dengan command `chmod`, setelah di ubah coba masuk lagi.

5. setelah masuk, sesuai petunjuk file password berada di direktori `/etc/bandit_pass/bandit14`, langsung saja cek file menggunakan `cat` 

```bash
cat /etc/bandit_pass/bandit14
```

Output: `MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS`

### Jawaban(Password)

```
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

---

Next -> [[Level 14 -> Level 15]]