# Laporan Praktikum Kriptografi
Minggu ke-: 12  
Topik: Aplikasi TLS & E-commerce
Nama: Resta Ariyandani 
NIM: 230202779  
Kelas: 5IKRA  

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

1. Menganalisis penggunaan kriptografi pada email dan SSL/TLS.
2. Menjelaskan enkripsi dalam transaksi e-commerce.
3. Mengevaluasi isu etika & privasi dalam penggunaan kriptografi di kehidupan         sehari-hari.

## 2. Dasar Teori
Transport Layer Security (TLS) adalah protokol yang berfungsi untuk mengamankan komunikasi di internet. TLS menjaga agar data yang dikirim antara pengguna (misalnya browser) dan server tetap rahasia, utuh, dan terverifikasi, sehingga pihak ketiga tidak dapat membaca atau mengubah informasi tersebut. Protokol ini umum digunakan pada layanan seperti HTTPS, email, dan berbagai aplikasi online. TLS bekerja dengan cara mengenkripsi data, memverifikasi identitas server (dan kadang klien) melalui sertifikat digital, serta memastikan integritas data selama pengiriman, sehingga transaksi online dan pertukaran informasi sensitif menjadi lebih aman.
---

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
1. Apa perbedaan utama antara HTTP dan HTTPS?
   Jawab :
   Perbedaan utama antara HTTP dan HTTPS terletak pada tingkat keamanan saat data     dikirimkan. HTTP mengirimkan informasi antara browser dan server tanpa             enkripsi, sehingga data sensitif seperti kata sandi bisa disadap atau diubah       oleh pihak ketiga. Sebaliknya, HTTPS menggunakan TLS/SSL untuk mengenkripsi        data, sehingga komunikasi tetap rahasia, utuh, dan terverifikasi. Dengan           demikian, HTTPS memungkinkan pengguna mengakses situs dan mentransfer informasi    dengan keamanan yang lebih tinggi dibanding HTTP.
2. Mengapa sertifikat digital menjadi penting dalam komunikasi TLS?
   Jawab :
   Sertifikat digital penting dalam komunikasi TLS karena berfungsi untuk             memverifikasi identitas server atau pihak yang terhubung dan mendukung             terciptanya koneksi yang aman. Dengan adanya sertifikat, browser atau klien        dapat memastikan bahwa server yang diakses benar-benar sah, sehingga mengurangi    risiko serangan man-in-the-middle (MITM). Selain itu, sertifikat juga              menyediakan kunci publik untuk mengenkripsi data, sehingga informasi yang          dikirim tetap rahasia dan tidak dapat diubah selama pengiriman. Singkatnya,        sertifikat digital menjadi pondasi keamanan TLS yang menjamin autentikasi dan      integritas komunikasi.
3. Bagaimana kriptografi mendukung privasi dalam komunikasi digital, tetapi           sekaligus menimbulkan tantangan hukum dan etika?
   Jawab :
   Kriptografi melindungi privasi komunikasi digital dengan mengenkripsi data,        sehingga hanya pihak berwenang yang dapat mengaksesnya. Namun, enkripsi kuat       juga bisa menyulitkan penegak hukum dan kadang disalahgunakan untuk aktivitas      ilegal, menimbulkan dilema antara privasi individu dan keamanan publik.
## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
