Prev -> [[Level 11 -> Level 12]]

---
Kata sandi untuk tingkat berikutnya disimpan dalam data **file.txt**, yang merupakan hedump dari file yang telah berulang kali dikompresi. Untuk tingkat ini mungkin berguna untuk membuat direktori di bawah /tmp di yang dapat Anda kerjakan. Gunakan mkdir dengan nama direktori yang sulit untuk menebak. Atau lebih baik, gunakan perintah "mktemp - d". Kemudian salut datafile menggunakan cp, dan mengganti namanya menggunakan mv 

---

# Write Up Level 12

Di level ini kata sandi tersimpan di dalam data file.txt, yang merupakan hedump dari  file yang telah berulang kali dikompresi. Di level ini kita akan mengerjakan nya di sebuah direktori bernama tmp untuk membuatnya menggukan perintah `"mktemp -d"`. kemudian salin datafile menggunakan cp, dan mengganti namanya menggunakan mv.

## Langkah Penyelesaian

1. Masuk ke server SSH bandit12 

```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
```

2. cek isi direktori, di dalam direktori ada file bertanama `data.txt` jika kita buka file ini berisi sebuah hexdump yang dimana file ini sudah di kompresi berkali kali maka tugas kita adalah mendekompresi file ini.

 3. coba kita analisa satu persatu, di soal kita di perintahkan mengerjakan nya di sebuah direktori bernama tmp, untuk membuat folder nya menggunakan command `mktemp -d` setelah itu muncul direktori `/tmp/tmp.6Yl4cyvXYP` sebelum masuk ke direktori tersebut kita copy file yang ada di direktori awal menggunakan command `cp data.txt <folder>`. setelah di copy masuk ke direktori tmp nya.

4. setelah berada di direktori tmp langsung eksekusi file menggunakan command `xxd -r data.txt > pw`,  artinya kita mereverse hex ke binery yang berada di data.txt lalu menyimpan ke file baru bernama `pw`.

5. setelah itu cek type file `pw` menggunakan command `file` output berupa `pw : gzip compressed data`, yang berati itu adalah file `gz` yang harus kita ekstrak, sebelum di ekstrak ganti nama file dengan extension yang sama yaitu `.gz`  dengan command `mv` 

```bash
mv pw pw.gz
```

6. setelah itu ekstrak file tersebut dengan command `gunzip` 

```bash
gunzip pw.gz
```

7. setelah itu buka file yang sudh diekstrak lalu cek lagi type filenya, ulangi langkah ini sampai menemukan file yang berisi kata sandi

	Terdapat 3 jenis file berbeda yaitu .gz, .gz2, dan tar cara mengekstrak nya juga dengan command berbeda sebagai berikut
	
	`gunzip` -> .gz
	`bunzip2` -> .gz2
	`tar -xf` -> tar

8. Ulangi hingga mendapatkan sebuah file bertype ASCII text

Final alur penyelesaian
```text
gz > gz2 > gz > tar > tar > bz2 > tar > gz > ASCII
```

File tersebut dikomprers 8x dan isi file terakhir adalah `The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn`.

## Jawaban(Password)

```
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```

---

Next ->  [[Level 13 -> Level 14]]