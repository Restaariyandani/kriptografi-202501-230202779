# Laporan Praktikum Kriptografi
Minggu ke-: 3  
Topik: Modular Math (Aritmetika Modular, GCD, Bilangan Prima, Logaritma Diskrit) 
Nama: Resta Ariyandani 
NIM: 230202779 
Kelas: 5IKRA 

---

## 1. Tujuan
Menyelesaikan operasi aritmatika modular, menentukan bilangan prima dan menghitung GCD (Greatest Common Divisor), dan menerapkan logaritma diskrit sederhana dalam simulasi kriptografi.

## 2. Dasar Teori
Matematika modular merupakan dasar penting dalam sistem kriptografi modern. Aritmatika modular bekerja dengan bilangan dalam ruang terbatas yang diatur oleh modulas, sehingga hasil operrasi seperti penjumlahan, perkalian, dan perpangkatan selalu bilangan besar dan menjadi inti algoritma seperti RSA, Diffie-Hellman, dan Elliptic Curve Cryptography (ECC).
Konsep FPB (GCD) digunakan untuk memastikan dua bilangan bersifat relatif prima, syarat penting dalam pembentukan kunci publik dan privat. Bilangan prima sendiri digunakan karena sulit difaktorkan, sehingga memperkuat keamanan algoritma seprti RSA.
Selain itu, logaritma diskrit kebalikan dari operasi perpangkatan dalam sistem modular menjadi dasar keamanan algoritma seperti Diffie-Hellman dan EIGamal, karena masalah ini sangat sulit diselesaikan secara komputasional.

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---

## 4. Source Code
1. Aritmatika modular
    def mod_add(a, b, n): return (a + b) % n
 def mod_sub(a, b, n): return (a - b) % n
 def mod_mul(a, b, n): return (a * b) % n
 def mod_exp(base, exp, n): return pow(base, exp, n)  # eksponensiasi modular

 print("7 + 5 mod 12 =", mod_add(7, 5, 12))
 print("7 * 5 mod 12 =", mod_mul(7, 5, 12))
 print("7^128 mod 13 =", mod_exp(7, 128, 13))

2. GCD & Algoritma Euclidean
     def gcd(a, b):
     while b != 0:
         a, b = b, a % b
     return a

 print("gcd(54, 24) =", gcd(54, 24))

 3. Extended Euclidean Algorithm
      def egcd(a, b):
if a == 0:
    return b, 0, 1
g, x1, y1 = egcd(b % a, a)
return g, y1 - (b // a) * x1, x1

def modinv(a, n):
    g, x, _ = egcd(a, n)
    if g != 1:
        return None
    return x % n

print("Invers 3 mod 11 =", modinv(3, 11))  # hasil: 4

4. Logaritma Diskrit
      def discrete_log(a, b, n):
     for x in range(n):
         if pow(a, x, n) == b:
             return x
     return None

 print("3^x ≡ 4 (mod 7), x =", discrete_log(3, 4, 7))  # hasil: 4
    

## 5. Hasil dan Pembahasan
Kode pertama memperlihatkan bagaimana operasi dasar seperti penjumlahan, perkalian, dan perpangkatan dapat dijalankan secara efisien di dalam sistem bilangan modular. Prinsip ini menjadi fondasi dari berbagai proses enkripsi dan dekripsi yang digunakan pada algoritma kriptografi modern, seperti RSA, karena semua operasi dilakukan dengan mempertahankan hasil dalam batas modulus tertentu.

Kemudian, bagian kode yang memuat algoritma GCD dan invers modular berfungsi untuk menjaga hubungan matematis antara dua bilangan. Perhitungan GCD digunakan untuk memastikan bahwa kedua bilangan tidak memiliki faktor persekutuan selain 1 (relatif prima), sedangkan invers modular memungkinkan pembalikan proses perhitungan, yakni dari hasil enkripsi kembali menjadi bentuk asli pada sistem kunci publik. Tanpa adanya invers modular, proses dekripsi tidak dapat dilakukan dengan benar. 

Terakhir, kode logaritma diskrit menggambarkan tingkat kesulitan dalam mencari nilai eksponen 𝑥 dari persamaan 𝑎 𝑥 ≡ 𝑏 ( mod 𝑛) a x ≡b(modn). Kompleksitas inilah yang menjadi dasar keamanan algoritma seperti Diffie–Hellman.

Secara keseluruhan, keempat potongan kode tersebut menggambarkan keterpaduan antara konsep matematika fundamental dan penerapannya dalam menjaga keamanan informasi digital. Melalui prinsip modular, GCD, invers modular, serta logaritma diskrit, kriptografi mampu melindungi data dari akses yang tidak sah dengan cara yang sistematis dan kuat secara matematis.

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](screenshots/output.png)
![Hasil Input](screenshots/input.png)
![Hasil Output](screenshots/output.png)
)

---

## 7. Jawaban Pertanyaan
1. Apa peran aritmetika modular dalam kriptografi modern? Jawab: Aritmetika modular menjadi dasar kriptografi modern karena menjaga perhitungan tetap efisien dan aman, serta digunakan dalam pembentukan dan perlindungan kunci enkripsi pada algoritma seperti RSA dan Diffie–Hellman.
2. Mengapa invers modular penting dalam algoritma kunci publik (misalnya RSA)? Jawab: Invers modular penting karena memungkinkan proses dekripsi membalik hasil enkripsi dalam algoritma kunci publik seperti RSA. Tanpa invers modular, pesan yang telah dienkripsi tidak dapat dikembalikan ke bentuk aslinya, sehingga sistem tidak dapat berfungsi dengan benar.
3. Apa tantangan utama dalam menyelesaikan logaritma diskrit untuk modulus besar? Jawab: Tantangan utama logaritma diskrit untuk modulus besar adalah sulit dan memakan waktu sangat lama untuk diselesaikan secara komputasional, karena tidak ada algoritma efisien untuk menemukan nilai eksponen ketika modulusnya besar.


## 8. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
