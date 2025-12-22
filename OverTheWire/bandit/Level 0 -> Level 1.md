Prev -> [[Level 0]]

---
# Level 0

Kata sandi untuk tingkat berikutnya disimpan dalam file yang disebut **Readme** yang terletak di direktori rumahan. Gunakan password ini untuk log ke bandit1 menggunakan SSH. Setiap kali Anda menemukan password untuk tingkat, Gunakan SSH (di port 2220) untuk masuk ke level itu dan melanjutkan permainan.

## Perintah yang mungkin Anda perlukan untuk menyelesaikan level ini

Basic Command linux

1. `ls` (list)
	Menampilkan isi direktori
	Fungsi: melihat file dan folder di suatu directory.

	contoh :
	`ls`

	menampilkan isi folder saat ini
	`ls -la`
	tampilkan semua file (termasuk yang tersembunyi) + detail

	Di CTF 
	Dipakai buat nyari file mencurigakaan kayak flag.txt, .hidden, dll.

2. `cd` (Change Directory)
	 Pindah folder
	 Contoh : `cd folder1`
	 masuk ke folder1
	 
	`cd ..`
	 naik 1 folder ke atas
	 
	`cd /`
	 pindah ke root directory
	 
	Di CTF: 
	Dipalai buat explore folder satu-satu cari flag.

3. `cat` (Concatenate)
	 Menampilkan isi file teks
	 contoh : `cat flag.txt`
	 menampilkan isi flag.txt
	 `cat reradme.txt`
	
	 Di CTF:
	 Command paling sering buat ambil flag
	 Kalau file besar, `cat` bisa spam layar.

4. `file`
	 Mengetahui jenis file
	 Fungsi: mengecek file itu teks, binary, image, archive, dll
	
	 contoh: `file flag`
	 output bisa:
	 flag: ASCII text
	 atau
	 `flag: ELF 64-bit executable`
	 
	 DI CTF:
	 Berguna kalau file tanpa ekstensi dan kamu bingung itu file apa

5. `du` (Disk Usage)
	Melihat ukuran file/folder
	contoh: `du -h`
	tampilkan ukuruan folder dalam format manusia (KB,MB)
	`du -ah`
	tampilkan ukuran file + folderr
	
	 DI CTF:
	 Dipakai buat:
	 - cari file aneh tapi ukuran besar
	 - Bandinginn foldler mana yang "Mencurigakan"

6. `find`
	Mencari file
	Fungsi: cari file berdasasrkan nama, ukuran, tipe, dll
	
	 contoh : `find . -name flag.txt`
	 
	 cari flalg.txt dari folder sekarang
	 `find / -name "*flag*" 2>/dev/null`
	 
	 cari semua file yang ada kata flag
	 `find . -type f`
	 cari semua file biasa(bukan folder)
	
	Di CTF:
	Command dewa buat cari flag yang di sembunyikan di folder dalam.

### Ringkasan Cepat (CTF mindset)

| Commad | Fungsi                 |
| ------ | ---------------------- |
| `ls`   | Lihat isi folder       |
| `cd`   | Masuk/Keluar folder    |
| `cat`  | Baca file/flag         |
| `file` | Cari tau jenis file    |
| `du`   | Cari file aneh         |
| `find` | Cari  flag tersembunyi |
**TIP:** Buat file untuk catatan dan kata sandi di mesin lokal Anda!

Kata sandi untuk level _tidak_ disimpan secara otomatis. Jika Anda tidak menyelamatkan mereka sendiri, Anda harus memulai dari bandit.

Password juga terkadang berubah. Disarankan untuk mencatat cara menyelesaikan setiap tantangan. Karena level semakin menantang, catatan terperinci berguna untuk kembali ke tempat yang Anda tinggalkan, referensi untuk masalah nanti, atau membantu orang lain setelah Anda menyelesaikan tantangan.

---
# Write Up Level 0

Setelah berhasil login ke server bandit, kita di berikan sebuah file readme di dalam Home untuk mengecek apa isi file tersebut kita akan menggunakan command Linux.

---

## Langkah Penyelesaian

1. Cek isi directory
	 Gunakan perintah `ls` untuk melihat file yang ada.

```bash
ls
```

Output:

```bash
bandit0@bandit:~$ ls
readme
```

2. Membaca isi file `readme`
	Setelah mengetahui bahwa terdapat file bernama `readme`, kita gunakan command `cat` untuk melihat isinya.

```bash
cat readme
```

Output :

```text
Congratulations on your first steps into the bandit game!!
Please make sure you have read the rules at https://overthewire.org/rules/
If you are following a course, workshop, walkthrough or other educational activity,
please inform the instructor about the rules as well and encourage them to
contribute to the OverTheWire community so we can keep these games free!

The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

---

## Jawaban (Password)

```
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```
Note : password ini akan di pakai di level berikut nya

---

Next → [[Level 1 ->  Level 2]]

---