# Laporan Praktikum Kriptografi
Minggu ke-: 10  
Topik:Public Key Infrastructure (PKI & Certificate Authority
Nama: Resta Ariyandani  
NIM: 230202779 
Kelas:5IKRA

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:
1. Membuat sertifikat digital sederhana.
2. Menjelaskan peran Certificate Authority (CA) dalam sistem PKI.
3. Mengevaluasi fungsi PKI dalam komunikasi aman (contoh: HTTPS, TLS).

## 2. Dasar Teori
Public Key Infrastructure (PKI) merupakan kerangka kerja yang digunakan untuk mengelola sistem keamanan berbasis kunci publik, termasuk pembuatan, penyimpanan, dan pemeriksaan sertifikat digital. PKI membantu memastikan bahwa proses enkripsi dan tanda tangan digital dilakukan secara aman dan terpercaya.

Certificate Authority (CA) adalah lembaga tepercaya di dalam PKI yang bertugas memverifikasi identitas pengguna serta mengeluarkan sertifikat digital. Secara umum, PKI dan CA saling melengkapi untuk menjaga keamanan, keaslian, dan kepercayaan dalam pertukaran informasi digital.

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
1. Apa fungsi utama Certificate Authority (CA)?
   Jawab :
   Fungsi utama Certificate Authority (CA) adalah bertindak sebagai pihak             tepercaya yang memastikan keaslian identitas suatu pengguna, perangkat, atau       organisasi dalam sistem keamanan digital. CA melakukan proses verifikasi           identitas sebelum menerbitkan sertifikat digital yang mengaitkan identitas         tersebut dengan kunci publik. Dengan adanya sertifikat ini, pihak lain dapat       mempercayai kunci publik yang digunakan dalam enkripsi maupun verifikasi tanda     tangan digital.
2. Mengapa self-signed certificate tidak cukup untuk sistem produksi?
   Jawab :
   Self-signed certificate kurang sesuai digunakan pada sistem produksi karena        tidak melalui proses validasi oleh lembaga tepercaya. Sertifikat ini dibuat dan    ditandatangani sendiri, sehingga identitas pemiliknya tidak dapat dipastikan       keasliannya. Kondisi tersebut membuat pengguna sulit mempercayai koneksi dan       meningkatkan risiko serangan keamanan, sehingga pada lingkungan produksi lebih     aman menggunakan sertifikat yang diterbitkan oleh Certificate Authority (CA)       resmi.
3. Bagaimana PKI mencegah serangan MITM dalam komunikasi TLS/HTTPS?
   Jawab :
   PKI membantu mencegah serangan Man-in-the-Middle (MITM) pada komunikasi            TLS/HTTPS dengan memastikan keaslian identitas server. Ketika koneksi HTTPS        dilakukan, server mengirimkan sertifikat digital yang telah disahkan oleh          Certificate Authority (CA). Peramban kemudian memeriksa validitas sertifikat       tersebut, termasuk tanda tangan CA dan kecocokan nama domain. Dengan proses        ini, klien dapat memastikan bahwa kunci publik yang digunakan benar-benar milik    server yang sah, sehingga pihak lain tidak dapat menyamar dalam komunikasi.

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
