Prev  -> [[Level 3 -> Level 4]]

---
Kata sandi untuk tingkat berikutnya disimpan hanya dalam satu-satunya yang dapat dibaca manusia. berkas di dalam **inhere**direktori di sini. Tip: jika terminal Anda kacau ke atas, cobalah perintah "reset".

## Perintah yang mungkin Anda perlukan untuk menyelesaikan level ini

[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html) , [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html) , [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html) , [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html) , [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html) , [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html)

Tips : Coba gunakan command `file` dan `strings`

---

# Write Up Level 4

Setelah menyelesaikan Level 3, pada Level 4 kita kembali login ke server SSH menggunakan akun **bandit4** dan password yang telah didapatkan dari level sebelumnya.

## Langkah Penyelesaian

1. Masuk ke server SSH bandit4

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

Setelah itu masukkan password yang didapat dari Level sebelumnya

2. Setelah masuk cek direktori home dengan command `ls`

3. Terdapat folder `inhere` langsung saja masuk ke folder tersebut dengan command  `cd`

4. cek isi folder `inhere` dengan command `ls`

Output:
```text
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file0
``` 

5. Terdapat 10 file langsung saja cek isi semua file sekaligus 

```bash
cat -- -file*
```

Output:

```text
�6);/:ˋd�Jhp␦r��}�k'���vj�7-(c\�;d��3�_~r��:#����b�2�Zn�SN:�4H���'MЗey�.�-W��� =��C�������z鈸1�[�;ҭ
�h�W�u8���;��޿�l�FP�I�m�&�����|3�=˸B�␦���S��/�Y["#���4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
�6�
   }�|&ڧa�C�9�̸n�q�dM'ό��w�=���[h+|�:[�P
                                       ��]K1�*~�w���
```

6. Terdapat teks yang tidak bisa di baca oleh manusia dan ada teks yang bisa di baca maka itu adalah password untuk lanjut ke password berikutnya

## Jawaban (Password)

```
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

---
Next -> [[Level 5 -> Level 6]]

