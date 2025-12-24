Prev -> [[Level 17 -> Level 18]]

---

Kata sandi untuk tingkat berikutnya disimpan dalam file **readme** diurutkan dengan homedirectry. Sayangnya, seseorang telah memodifikasi **.bashrc** untuk log Anda keluar ketika Anda login dengan SSH.

---

# Write Up Level 18

### Level 18

Deskrirpsi:
	Terdapat sebuah kata sandi yang disimpan di dalam file **readme** di dirertori Home, sayangnya ada seseorang yang memodifikasi **.bashrc** , jika login dengan SSH maka otomatis akan Logout.

### Analisis

Kata sandi tersimpan di dalam Home direktori dengan nama file **readme** jika login dengan SSH maka otomatis akan langsung keluar, lokasi file password sudah diketahui maka kita langsung ambil password tersebut.

### Langkah Penyelesaian

1. Masuk server SSH dengan bandit18 dan tambahkan command `cat` untuk melihat isi file `readme`, jika kita tidak bisa login dan mengecek maka kita harus langsung mengecek file tersebut tanpa harus masuk, hanya memasukan password dari level sebelumnya saja.

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
```


### Jawaban(Password)

```
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```

---

Next -> [[Level 19 -> Level 20]]
