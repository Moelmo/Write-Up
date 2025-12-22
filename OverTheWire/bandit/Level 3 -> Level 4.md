Prev -> [[Level 2 -> Level 3]]

---

Kata sandi untuk tingkat berikutnya disimpan dalam file tersembunyi di **inhere** sebuah direktori.

## Perintah yang mungkin Anda perlukan untuk menyelesaikan level ini

[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html) , [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html) , [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html) , [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html) , [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html) , [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html)

----

# Write Up Level 3

Setelah menyelesaikan Level 2, pada Level 3 kita kembali login ke server SSH menggunakan akun **bandit3** dan password yang telah didapatkan dari level sebelumnya.

## Langkah Penyelesaian

1. Masuk ke server SSH bandit3

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

Setelah itu masukkan password dari level 2

2. Cek isi direktori Home

```bash
ls
```

Output :

```text
inhere
```

3. Masuk ke folder `inhere`

```bash
cd inhere
```

Setelah itu cek lagi isi dalam folder dengan command `ls -a`.
File tersembunyi di Linux biasanya diawali dengan tanda titik (`.`), sehingga tidak terlihat dengan `ls` biasa. Oleh karena itu digunakan `ls -a` untuk menampilkan seluruh file termasuk hidden file.

4. Terdapat File dengan nama `...Hiding-From-You` setelah itu coba cek isi file nya

```bash
cat ./...Hiding-From-You
```

Output:

```text
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```

## Jawaban (Password)

```
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```

---

Next -> [[Level 4 -> Level 5]]