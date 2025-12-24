Prev -> [[Level 15 -> Level 16]]

---

Kredensial untuk tingkat berikutnya dapat diambil dengan mengirimkan kata sandi tingkat saat ini ke **port di localhost di kisaran 31000 sampai 32000.** Pertama cari tahu port mana yang memiliki server mendengarkan mereka. Kemudian cari tahu siapa dari mereka yang berbicara SSL/TLS dan mana yang tidak. Hanya ada 1 server yang akan memberikan kredensial berikutnya, Orang lain hanya akan mengirim kembali kepada Anda apa pun yang Anda kirim ke dalamnya.

---

# Write Up Level 16

### Level 16

Deskripsi:
	Kredensial untuk lanjut ke level berikutnya, dapat di ambil dengan mengirimkan kata sandi level saat ini ke port di localhost kisaran 31000 sampai 32000, pertama cari tahu port mana yang memiliki server mendengarkan, kemudian cari tahu siapa dari mereka memakai SSL/TLS dan mana yang tidak. Hanya ada 1 server yang akan memberikan Kredensial.


### Analisis

Dalam soal terdapat sebauh port 31000 hingga 32000, hanya ada 1 port yang aktif, kemudian cari tau mereka memakai SSL/TLS dan mana yang tidak, hanya ada 1 server yang memberikan Kredensial.

### Langkah Penyelesaian

1. Masuk ke server bandit16

```bash
ssh bandit16@bandit.labs.overthewire.org -p 2220
```

2. Scan port yang aktif di localhost di kisaran 31000-32000

```bash
nmap -p 31000-32000 -sV localhost
```

Output: 

```text
PORT      STATE SERVICE     VERSION
31046/tcp open  echo
31518/tcp open  ssl/echo
31691/tcp open  echo
31790/tcp open  ssl/unknown
31960/tcp open  echo
```

3. Di lihat di port terdapat 2 port yang akan membalas dan salah satu itu hanya akan mengembalikan pesan yang kita kirirm, maka port yang aktif adalalh `31790`  setelah mengetahui port yang akan mengirimkan kredensial langsung masuk ke port tersebut lalu masukan kata sandi yang  dipakai masuk di level ini.

```bash
ncat --ssl localhost 31790
```

Ouput: 

```text
-----BEGIN RSA PRIVATE KEY-----
...
...
...
-----END RSA PRIVATE KEY-----
```

4. Setelah mendapatkan private key copy lalu buat file di komputer anda sendiri, setelah itu paste ke file yang telah dibuat, file tersebut untuk masuk ke Level berikutnya

### Jawaban(Password)

```
file.txt (berisi private key)
```

---

Next -> [[Level 17 -> Level 18]]