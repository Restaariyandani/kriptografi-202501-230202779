# Laporan Praktikum Kriptografi
Minggu ke-: 7  
Topik: Diffie-Hellman Key Exchange  
Nama: Resta Ariyandani
NIM: 230202779  
Kelas:5IKRA 

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

1. Melakukan simulasi protokol Diffie-Hellman untuk pertukaran kunci publik.
2. Menjelaskan mekanisme pertukaran kunci rahasia menggunakan bilangan prima dan      logaritma diskrit.
3. Menganalisis potensi serangan pada protokol Diffie-Hellman (termasuk serangan      Man-in-the-Middle / MITM).

## 2. Dasar Teori
Diffie–Hellman Key Exchange adalah metode yang digunakan untuk memungkinkan dua pihak berbagi kunci rahasia yang sama melalui jaringan terbuka tanpa harus mengirimkan kunci tersebut secara langsung. Metode ini memanfaatkan perhitungan matematika khusus sehingga meskipun proses pertukaran dapat dilihat oleh pihak lain, kunci rahasia yang dihasilkan tetap aman.
## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )


## 4. Source Code
import random

# parameter umum (disepakati publik)
p = 23  # bilangan prima
g = 5   # generator

# private key masing-masing pihak
a = random.randint(1, p-1)  # secret Alice
b = random.randint(1, p-1)  # secret Bob

# public key
A = pow(g, a, p)
B = pow(g, b, p)

# exchange public key
shared_secret_A = pow(B, a, p)
shared_secret_B = pow(A, b, p)

print("Kunci bersama Alice :", shared_secret_A)
print("Kunci bersama Bob   :", shared_secret_B)

---

## 5. Hasil dan Pembahasan

![Hasil Eksekusi](screenshots/kriptoweek7.png)


---

## 6. Jawaban Pertanyaan
1. Mengapa Diffie-Hellman memungkinkan pertukaran kunci di saluran publik?
   Jawab :
   Diffie-Hellman memungkinkan dua pihak membentuk kunci rahasia yang sama tanpa      harus mengirimkan kunci tersebut secara langsung melalui jaringan. Informasi       yang dikirimkan secara terbuka hanyalah parameter umum seperti bilangan publik     dan nilai hasil perhitungan masing-masing pihak. Meskipun nilai-nilai tersebut     dapat diketahui oleh pihak lain, kunci rahasia tetap tidak dapat diperoleh         karena untuk menentukannya diperlukan penyelesaian masalah logaritma diskret,      yang sangat sulit diselesaikan secara matematis.
2. Apa kelemahan utama protokol Diffie-Hellman murni?
   Jawab :
   Kelemahan utama dari Diffie-Hellman murni terletak pada tidak adanya proses        verifikasi identitas. Hal ini membuatnya mudah disusupi oleh serangan man-in-      the-middle, di mana pihak lain dapat berpura-pura menjadi lawan komunikasi dan     membentuk kunci rahasia tanpa diketahui oleh kedua pihak yang sebenarnya.
3. Bagaimana cara mencegah serangan MITM pada protokol ini?
   Jawab :
   Serangan Man-in-the-Middle (MITM) pada protokol Diffie-Hellman dapat dicegah       dengan menambahkan mekanisme autentikasi. Salah satu caranya adalah                menggabungkan Diffie-Hellman dengan sertifikat digital atau tanda tangan           digital, sehingga identitas masing-masing pihak dapat diverifikasi. Selain itu,    penggunaan protokol keamanan seperti TLS/SSL juga efektif karena menyediakan       proses pertukaran kunci yang aman sekaligus terautentikasi, sehingga mencegah      pihak ketiga menyusup ke dalam komunikasi.

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
