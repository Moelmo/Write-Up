Prev -> [[Level 14 -> Level 15]]

---

Kata sandi untuk tingkat berikutnya dapat diambil dengan mengirimkan kata sandi dari tingkat saat ini untuk **port 300001 pada hosting lokal** menggunakan Enkripsi SSL/TLS.

**Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.**

---

# Write Up Level 15

### Level 15

Deskripsi :
	Kata sandi untuk level berikutnya dapat diambil dengan mengirimkan kata sandi dari level sebelumnya, kirim kata sandi level sebelumnya di port 300001 pada localhost menggunakan Enkripsi SSL/TLS.

### Analisis

Soal yang diberikan mengharuskan kita mengirim kata sandi dari level sebelumnya di port 300001 pada localhost dengan menggunakan Enkripsi SSL/TLS, untuk agar bisa terhubung ke localhost tersebut kita memakai command `openssl s_client`.

### Langkah Penyelesaian

1. Masuk ke server bandit15
```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220
```

2. hubungkan ke localhost port 300001 dengan menggunakan openssl, dan kirim kata sandi dari level sebelumnya, jika benar maka akan di balas dengan mengirimkan kata sandi untuk level berikutnya.

```bash
openssl s_client -connect localhost:300001
```

### Jawaban(Password)

```
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```

---

Next -> [[Level 16 -> Level 17]]