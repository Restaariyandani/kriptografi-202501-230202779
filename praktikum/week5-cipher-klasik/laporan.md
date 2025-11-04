# Laporan Praktikum Kriptografi
Minggu ke-: 5 
Topik: Cipher Klasik (Caesar, Vigenère, Transposisi)  
Nama: Resta Ariyandani  
NIM: 230202779  
Kelas: 5IKRA  



## 1. Tujuan
Menerapkan algoritma Caesar Cipher untuk enkripsi dan dekripsi teks, Menerapkan algoritma Vigenère Cipher dengan variasi kunci, Mengimplementasikan algoritma transposisi sederhana, Menjelaskan kelemahan algoritma kriptografi klasik.
## 2. Dasar Teori
Cipher klasik adalah teknik penyandian informasi yang berkembang sebelum hadirnya teknologi komputer dan sistem kriptografi modern. Metode ini bekerja dengan cara mengganti atau menukar posisi karakter dalam teks asli (plaintext) sehingga terbentuk pesan baru yang tersamarkan dan sulit dipahami, yang disebut ciphertext.
1. Cipher Substitusi
   a. Caesar Cipher (Cipher Geser)
   Caesar Cipher bekerja dengan menggeser setiap huruf dalam plaintext sejauh jumlah posisi tertentu di dalam alfabet. Pergeseran ini ditentukan oleh nilai kunci (key) yang sama untuk semua huruf. dan untuk mekanismenya yaitu Caesar Cipher menggunakan aritmatika modular 26, karena terdapat 26 huruf dalam alfabet latin. Setiap huruf diubah menjadi angka (A=0, B=1,...,Z=25). Untuk kelemahannya itu hanya memiliki 25 kemungkinana kunci itu mudah dipecahkan menggunakan brute force dan frekuensi huruf tetap terlihat, sehingga dapat diaanalisis dengan analisis frekuensi.
 2. Cipher Transposisi
    a. Transposisi Cipher (Misal: Columnar Transposition)
    olumnar Transposition Cipher, huruf-huruf dalam pesan asli ditulis dalam bentuk tabel (kolom) sesuai panjang kunci yang digunakan. Setelah semua huruf diisi ke dalam tabel secara berurutan, ciphertext dibentuk dengan membaca huruf-huruf secara kolom mengikuti urutan huruf dari kunci. Untuk mekanismenya Tentukan kunci (misalnya, sebuah kata yang urutan hurufnya diindeks), Tulis plaintext secara horizontal di bawah kunci, Baca teks secara vertikal, mengikuti urutan numerik dari huruf-huruf kunci tersebut. Dan Untuk kelemahannya itu tidak mengubah huruf, hanya urutannya sehingga frekuensi huruf tetap sama dan dapat dianalisis dan rentan terhadap serangan kriptanalisasi pola, terutama jika pesan cukup panjang.

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

## 4. Source Code
(Salin kode program utama yang dibuat atau dimodifikasi.  
Gunakan blok kode:

```python
# contoh potongan kode
def encrypt(text, key):
    return ...
```
)

---

## 5. Hasil dan Pembahasan
(- Lampirkan screenshot hasil eksekusi program (taruh di folder `screenshots/`).  
- Berikan tabel atau ringkasan hasil uji jika diperlukan.  
- Jelaskan apakah hasil sesuai ekspektasi.  
- Bahas error (jika ada) dan solusinya. 

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](screenshots/output.png)
![Hasil Input](screenshots/input.png)
![Hasil Output](screenshots/output.png)
)

---

## 6. Jawaban Pertanyaan
1. Apa kelemahan utama algoritma Caesar Cipher dan Vigenère Cipher? Jawab: Kelemahan utama Caesar Cipher terletak pada jumlah kunci yang sangat terbatas dan pola pergeseran huruf yang mudah dikenali. Dengan hanya 25 kemungkinan kunci, cipher ini rentan terhadap serangan brute force maupun analisis frekuensi huruf. Sedangkan Vigenère Cipher memiliki kelemahan karena kunci yang digunakan cenderung berulang. Pengulangan ini memungkinkan penyerang untuk menentukan panjang kunci melalui metode seperti Kasiski atau Friedman, sehingga pesan yang dienkripsi masih bisa dipecahkan meskipun algoritmanya terlihat lebih kompleks dibanding Caesar Cipher.
2. Mengapa cipher klasik mudah diserang dengan analisis frekuensi? Jawab: Cipher klasik rentan terhadap analisis frekuensi karena mereka tidak menghapus pola kemunculan huruf dalam bahasa asli. Algoritma seperti Caesar atau substitusi monoalfabetik hanya mengganti tiap huruf dengan huruf lain, sehingga proporsi huruf yang sering muncul tetap sama. Penyerang cukup menghitung frekuensi huruf pada teks terenkripsi dan mencocokkannya dengan frekuensi bahasa asli untuk menebak substitusi dan mengungkap pesan.
3. Bandingkan kelebihan dan kelemahan cipher substitusi vs transposisi. Jawab: a. Cipher Substitusi: Kelebihan: Relatif sederhana dan cepat diterapkan dan Mengubah huruf asli sehingga pesan terlihat berbeda secara langsung. Kelemahan: Pola frekuensi huruf tetap terlihat, sehingga mudah diserang dengan analisis frekuensi dan Rentan terhadap brute force jika ruang kunci kecil. b. Cipher Transposisi: Kelebihan: Pola huruf asli tidak hilang, tetapi urutan huruf diacak, sehingga analisis frekuensi lebih sulit langsung digunakan dan Dapat digabungkan dengan substitusi untuk meningkatkan keamanan. Kelemahan: Pesan masih mempertahankan huruf asli, sehingga pola tertentu (seperti pengulangan kata) bisa memberi petunjuk dan Lebih rumit untuk diimplementasikan dibanding substitusi sederhana.


## 7. Commit Log

commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
