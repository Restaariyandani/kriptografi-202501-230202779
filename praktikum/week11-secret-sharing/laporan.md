# Laporan Praktikum Kriptografi
Minggu ke-:11  
Topik:Secret Sharing (Shamir’s Secret Sharing)  
Nama: Resta Ariyandani 
NIM: 230202779  
Kelas:5IKRA 

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

1. Menjelaskan konsep Shamir Secret Sharing (SSS).
2. Melakukan simulasi pembagian rahasia ke beberapa pihak menggunakan skema SSS.
4. Menganalisis keamanan skema distribusi rahasia.

## 2. Dasar Teori
Shamir Secret Sharing (SSS) merupakan sebuah teknik kriptografi yang berfungsi untuk membagi sebuah rahasia menjadi beberapa bagian sehingga setiap bagian saja tidak cukup untuk mengungkap rahasia tersebut. Rahasia hanya bisa dipulihkan jika sejumlah bagian tertentu, yang disebut threshold, dikumpulkan. Metode ini ditemukan oleh Adi Shamir pada tahun 1979 dan memanfaatkan polinomial dengan derajat tertentu, di mana rahasia asli ditempatkan sebagai koefisien konstanta. Setiap bagian atau share mewakili titik pada polinomial, dan minimal jumlah share sesuai threshold diperlukan untuk melakukan interpolasi polinomial agar rahasia asli bisa diperoleh kembali. Dengan pendekatan ini, Shamir Secret Sharing memungkinkan penyimpanan atau distribusi rahasia secara aman, karena jika jumlah share yang tersedia kurang dari threshold, rahasia tetap tidak dapat diakses. Teknik ini banyak diterapkan dalam manajemen kunci, sistem backup aman, dan berbagai aplikasi kriptografi.

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---


## 6. Source Code
from secrets import randbelow

P = 208351617316091241234326746312124448251235562226470491514186331217050270460481

def split_secret(secret, k, n):
    secret = int.from_bytes(secret.encode(), 'big')
    coeffs = [secret] + [randbelow(P) for _ in range(k - 1)]
    shares = []
    for i in range(1, n + 1):
        y = sum(coeffs[j] * pow(i, j, P) for j in range(k)) % P
        shares.append((i, y))
    return shares

def recover_secret(shares):
    secret = 0
    for j, (xj, yj) in enumerate(shares):
        prod = 1
        for m, (xm, _) in enumerate(shares):
            if m != j:
                prod *= xm * pow(xm - xj, -1, P)
                prod %= P
        secret += yj * prod
        secret %= P
    return secret

secret = "KriptografiUPB2025"
shares = split_secret(secret, 3, 5)
print("Shares:", shares)

recovered = recover_secret(shares[:3])
print("Recovered secret:", recovered.to_bytes((recovered.bit_length()+7)//8,'big').decode())

## 7. Hasil dan Pembahasan
(- Lampirkan screenshot hasil eksekusi program (taruh di folder `screenshots/`).  
- Berikan tabel atau ringkasan hasil uji jika diperlukan.  
- Jelaskan apakah hasil sesuai ekspektasi.  
- Bahas error (jika ada) dan solusinya. 

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](screenshots/kriptoweek11.png)

---

## 8. Jawaban Pertanyaan
1. Apa keuntungan utama Shamir Secret Sharing dibanding membagikan salinan kunci      secara langsung?
   Jawab :
   Keuntungan utama Shamir Secret Sharing dibanding membagikan salinan kunci          langsung adalah keamanannya. Setiap bagian saja tidak bisa mengungkap rahasia,     sehingga kehilangan atau bocornya sebagian share tidak membahayakan. Rahasia       hanya bisa dipulihkan jika sejumlah share sesuai threshold digabung, sekaligus     memberi kontrol dan fleksibilitas lebih dibanding pembagian kunci langsung.
2. Apa peran threshold (k) dalam keamanan secret sharing?
   Jawab :
   Dalam secret sharing, threshold (k) menunjukkan jumlah minimal share yang harus    digabungkan untuk mendapatkan rahasia asli. Threshold berperan penting dalam       keamanan karena menghalangi pihak yang memiliki share kurang dari k untuk          mengakses rahasia. Semakin besar nilai k, semakin sulit rahasia disalahgunakan,    sehingga threshold bertindak sebagai pengatur keamanan agar hanya pihak yang       cukup banyak yang bisa memulihkan rahasia.
3. Berikan satu contoh skenario nyata di mana SSS sangat bermanfaat.
   Jawab :
   Contoh nyata penggunaan Shamir Secret Sharing (SSS) adalah dalam pengelolaan       kunci perusahaan atau cryptocurrency. Misalnya, sebuah perusahaan memiliki         kunci privat dompet cryptocurrency yang sangat penting. Alih-alih menyimpan        kunci secara utuh yang berisiko dicuri atau hilang, kunci tersebut dibagi          menjadi beberapa bagian menggunakan SSS, misalnya 5 share dengan threshold 3.      Artinya, minimal 3 dari 5 eksekutif harus bekerja sama untuk mengakses kunci       dan melakukan transaksi. Dengan begitu, jika satu atau dua share hilang atau       dicuri, rahasia tetap aman, sehingga risiko kehilangan aset atau kebocoran         kunci dapat diminimalkan.

---

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
