Tujuan dari level ini adalah agar Anda masuk ke dalam permainan menggunakan SSH. Host yang Anda butuhkan untuk terhubung adalah **bandit.labs.overthewire.org**, di pelabuhan 2220. Nama pengguna adalah **bandit0** dan password adalah **bandit.** Sekaligus login, pergi ke halaman [Level 1](https://overthewire.org/wargames/bandit/bandit1.html) untuk mengetahui cara mengalahkan Level 1.

## Perintah yang mungkin Anda perlukan untuk menyelesaikan level ini

[ssh](https://manpages.ubuntu.com/manpages/noble/man1/ssh.1.html)

## Bahan Bacaan yang Bermanfaat

- [Secure Shell (SSH) di Wikipedia](https://en.wikipedia.org/wiki/Secure_Shell)
- [Cara menggunakan SSH dengan port non-standar di Its FOSS](https://itsfoss.com/ssh-to-port/)
- [Cara menggunakan SSH dengan ssh-keys pada wikiHow](https://www.wikihow.com/Use-SSH)

## 1️⃣ Secure Shell (SSH) – Wikipedia

### Apa itu SSH?

**SSH (Secure Shell)** adalah **cara aman untuk masuk ke komputer lain lewat jaringan (internet)** menggunakan terminal.

📌 Biasanya dipakai untuk:

- Login ke server
- Mengontrol server jarak jauh
- Transfer file dengan aman

### Kenapa disebut “Secure”?

Karena:

- Data **dienkripsi**
- Username & password **tidak dikirim polos**
- Lebih aman dari telnet

### Contoh penggunaan:

`ssh user@server`

➡️ Kamu masuk ke komputer lain dari terminal.

📎 Di CTF:

- Hampir semua challenge **login pakai SSH**
- Contoh OverTheWire Bandit

---

## 2️⃣ How to use SSH with a non-standard port – It’s FOSS

### Apa maksud _non-standard port_?

Secara default, SSH pakai:

`Port 22`

Tapi kadang server pakai **port lain**, misalnya:

`2222`

Ini disebut **non-standard port**.

---

### Cara pakai SSH dengan port berbeda

Gunakan opsi `-p`:

`ssh -p 2222 user@server`

Artinya:

- `-p 2222` → pakai port 2222
- `user@server` → akun & alamat server

---

### Kenapa port diganti?

- Mengurangi serangan otomatis
- Keamanan tambahan
- Konfigurasi khusus server

📎 Di CTF:

- Sering banget SSH **tidak pakai port 22**
- Kalau salah port → **tidak bisa login**

---

## 3️⃣ How to use SSH with ssh-keys – wikiHow

### Apa itu SSH key?

**SSH key** adalah **kunci digital** sebagai pengganti password.

Terdiri dari:

- **Private key** → disimpan di komputer kamu
- **Public key** → disimpan di server

---

### Kenapa pakai SSH key?

- Lebih aman dari password
- Login lebih cepat
- Tidak perlu ketik password tiap kali

---

### Cara kerja singkat (logika gampang)

1. Kamu punya kunci
2. Server punya pasangan kuncinya
3. Kalau cocok → masuk

---

### Contoh login pakai SSH key

`ssh user@server`

➡️ Langsung masuk **tanpa password**

📎 Di dunia nyata:

- Admin server
- DevOps
- GitHub SSH
- Server production

---

## 🧠 Ringkasan Cepat

|Topik|Intinya|
|---|---|
|SSH|Login aman ke server|
|Non-standard port|SSH pakai port selain 22|
|SSH key|Login tanpa password|

---

## 🎯 Kesimpulan

Ketiga materi ini penting untuk:

- Linux
- Cybersecurity
- CTF
- Server & networking

---

# Write Up Level 1

"Dari soal yang ada di Level 0 ini kita di suruh login ke server *bandit.labs.overthewire.org* dengan port *2220*, Dengan Username bandit0 dan password yang sama bandit0"

> Penyelesaian kita akan menggunakaan command bernama `ssh`
> jawaban : ssh bandit0@bandit.labs.overthewire.org -p 2220
> password : bandit0

Next -> [[Level 0 -> Level 1]]