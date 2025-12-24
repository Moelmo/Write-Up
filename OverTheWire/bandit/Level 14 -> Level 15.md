Prev -> [[Level 13 -> Level 14]]

---
Kata sandi untuk tingkat berikutnya dapat diambil dengan mengirimkan kata sandi dari tingkat saat ini untuk **port 30000 di localhost.**

## Perintah yang mungkin Anda perlukan untuk menyelesaikan level ini

ssh, telnet, nc, openssl, s_client, nmap

---

# Write Up Level 14

### Level 14

Deskripsi:
	Kata sandi untuk level selanjutnya dapat diambil dengan mengirimkan kata sandi dari level sebelumnya dengan port 3000 di localhost

### Analisis

Dari soal tersebut kita hanya disuruh mengirimkan kata sandi yang sudah didapat di level sebelumnya dan dikirimkan ke localhost dengan port 3000, tools yang kita pakai adalah `nc` 

> **nc (netcat)** adalah tool untuk **mengirim dan menerima teks/data langsung lewat port jaringan**.
	Singkatnya:  **nc = alat ngobrol langsung ke sebuah port.**


### Langkah Penyelesaian

1. Masuk ke server bandit14

```bash
ssh bandit14@bandit.labs.overthewire.org -p 2220
```

2.  setelah masuk, sesuai soal yang diberikan kita diharuskan mengirim password dari level sebelumnya ke localhost dengan port 3000, dengan menggunakan command `nc localhost 3000` , setelah itu kita diharuskan mengirim pesan ke port tersebut pesan nya adalah password di level sebelumnya. setelah dikirim maka akan mendapatkan balasan yaitu password untuk level berikutnya.

### Jawaban(Password)

```
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

---

Next -> [[Level 15 -> Level 16]]