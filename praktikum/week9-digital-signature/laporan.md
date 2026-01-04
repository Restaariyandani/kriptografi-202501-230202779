# Laporan Praktikum Kriptografi
Minggu ke-: 9 
Topik: Digital Signature (RSA/DSA)
Nama: Resta Ariyandani 
NIM: 230202779  
Kelas:5IKRA 

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:
1. Mengimplementasikan tanda tangan digital menggunakan algoritma RSA/DSA.
2. Memverifikasi keaslian tanda tangan digital.
3. Menjelaskan manfaat tanda tangan digital dalam otentikasi pesan dan integritas     data.

## 2. Dasar Teori
Digital Signature (RSA/DSA) merupakan teknik keamanan yang berfungsi untuk menjamin bahwa sebuah pesan atau data benar-benar berasal dari pihak yang sah dan tidak mengalami perubahan. Prosesnya dilakukan dengan menggunakan kunci privat untuk membuat tanda tangan, lalu diverifikasi menggunakan kunci publik. RSA dan DSA adalah algoritma yang banyak digunakan dalam penerapan tanda tangan digital untuk memastikan keaslian dan integritas data.

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---

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
1. Apa perbedaan utama antara enkripsi RSA dan tanda tangan digital RSA?
   Jawab :
   Perbedaan utama antara RSA untuk enkripsi dan RSA untuk tanda tangan digital       terletak pada fungsi dan cara penggunaan kuncinya. Enkripsi RSA bertujuan          melindungi isi pesan agar tetap rahasia dengan mengenkripsi data menggunakan       kunci publik milik penerima. Sebaliknya, tanda tangan digital RSA digunakan        untuk membuktikan bahwa pesan berasal dari pengirim yang sah dan tidak diubah,     dengan cara menandatangani pesan menggunakan kunci privat pengirim lalu            memverifikasinya menggunakan kunci publik pengirim.
2. Mengapa tanda tangan digital menjamin integritas dan otentikasi pesan?
   Jawab :
   Tanda tangan digital dapat menjamin integritas pesan karena tanda tangan           tersebut dibuat berdasarkan isi pesan, sehingga jika pesan mengalami perubahan     sekecil apa pun, hasil verifikasinya akan menjadi tidak valid. Selain itu,         tanda tangan digital juga menjamin otentikasi pengirim, karena proses              penandatanganan menggunakan kunci privat yang hanya dimiliki oleh pengirim yang    sah, sehingga penerima dapat memastikan bahwa pesan benar-benar berasal dari       pihak yang tepat.
3. Bagaimana peran Certificate Authority (CA) dalam sistem tanda tangan digital       modern?
   Jawab :
   Certificate Authority (CA) berfungsi sebagai lembaga tepercaya yang memvalidasi    identitas pemilik kunci dalam sistem tanda tangan digital. CA menerbitkan          sertifikat digital yang menghubungkan identitas pengguna dengan kunci              publiknya, sehingga penerima dapat yakin bahwa kunci publik yang digunakan         untuk verifikasi tanda tangan memang milik pihak yang benar dan dapat dipercaya.

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
