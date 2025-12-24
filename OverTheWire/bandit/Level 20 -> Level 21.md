Prev -> [[Level 19 -> Level 20]]

---

Ada biner yang terpisah dalam homedirector yang melakukan berikut: itu membuat koneksi ke localhost di pelabuhan Anda yang ditentukan sebagai argumen commandline. Kemudian membaca sederet teks dari koneksi dan membandingkannya dengan password di tingkat sebelumnya (bandit20). Jika password yang benar, itu akan mengirimkan password untuk tingkat berikutnya (bandit21).

----

# Write Up Level 20

### Level 20 

Deskripsi :
Terdapat sebuah **setuid binary** yang bekerja dengan cara:

1. Menghubungi `localhost` pada **port yang ditentukan sebagai argumen**
2. Membaca **satu baris teks** dari koneksi tersebut
3. Membandingkannya dengan **password Bandit20**
4. Jika password benar, binary akan **mengirimkan password Bandit21**

---

## Analisis

Binary tersebut berjalan sebagai **client**, bukan server.  
Artinya:

- Binary akan **menghubungi kita**
- Kita harus menyediakan **server lokal** yang siap menerima koneksi

Untuk membuat server sederhana, digunakan tool **`nc` (netcat)**.

Karena binary bersifat **setuid**, ia memiliki hak akses untuk membaca file password Bandit21 yang tidak bisa diakses user biasa.

---

### Solusi

1. Membuat listener lokal menggunakan `nc`
2. Menjalankan binary setuid dengan port yang sama
3. Mengirim password Bandit20 melalui koneksi tersebut
4. Menerima password Bandit21 sebagai balasan

---

### Langkah-Langkah Penyelesaian

1. Menentukan Port Pilih satu port bebas, misalnya:`4444`, Port ini harus digunakan oleh `nc` dan binary setuid.


 2. Menjalankan Listener (Server), Di terminal pertama, jalankan `nc` dalam mode listen:

```bash
nc -l 4444
```

Terminal ini akan menunggu koneksi dari binary.

3. Menjalankan Binary Setuid. Di terminal kedua, jalankan binary setuid dengan port yang sama:

```
./suconnect 4444
```

Binary akan langsung mencoba terhubung ke listener.

4. Mengirim Password Bandit20

	Setelah koneksi berhasil:
	- Kembali ke terminal `nc`
	- Masukkan password **Bandit20**
	- Tekan ENTER

 5. Menerima Password Bandit21 Jika password yang dikirim benar:
	- Binary akan mengirimkan password **Bandit21**
	- Password tersebut tampil di terminal `nc`


### Password(Jawaban)

```
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```

---

Next -> [[Level 21 -> Level 22]]