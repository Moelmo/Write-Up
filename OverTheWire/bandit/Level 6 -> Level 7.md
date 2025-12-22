Prev -> [[Level 5 -> Level 6]]

---
Kata sandi untuk tingkat berikutnya disimpan **di suatu tempat di server** dan memiliki semua properti berikut:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

---

# Write Up Level  6

Di level 6 ini, diberikan soal yang mengharuskan kita mencari sebuah kata sandi di suatu tempat di server, dengan clue

- user bandit7
- group bandit6
- ukuran 33 byte

## Langkah Penyelesaian

1. Masuk ke server SSH bandit 6 dan masukkan password yang di dapat di level sebelumnya

```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```

2. setelah masuk server kita cek direktori ada apa saja, setelah di cek tidak ada apa apa di dalam direktori

3. di dalam direktori kosong tidak ada file apapun, dengan clue yang di kasih yaitu file tersebut dimiliki oleh user bandit7 di group bandit6 dan ukuran file 33 byte, untuk mencari file tersebut kita pakai command `find` 

```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

4. dan terdapat lokasi kata sandi `/var/lib/dpkg/info/bandit7.password`, setelah mendapatkan lokasi kata sandinya langsung saja kita cek menggunakan `cat <lokasi direktori>`, dan terdapat sebuah kata sandi untuk level berikutnya

## Jawaban (Password)

```
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

---

Next -> [[Level 7 -> Level 8]]