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
from cryptography import x509
from cryptography.x509.oid import NameOID
from cryptography.hazmat.primitives import hashes, serialization
from cryptography.hazmat.primitives.asymmetric import rsa
from datetime import datetime, timedelta

# Generate key pair
key = rsa.generate_private_key(public_exponent=65537, key_size=2048)

# Buat subject & issuer (CA sederhana = self-signed)
subject = issuer = x509.Name([
    x509.NameAttribute(NameOID.COUNTRY_NAME, u"ID"),
    x509.NameAttribute(NameOID.ORGANIZATION_NAME, u"UPB Kriptografi"),
    x509.NameAttribute(NameOID.COMMON_NAME, u"example.com"),
])

# Buat sertifikat
cert = (
    x509.CertificateBuilder()
    .subject_name(subject)
    .issuer_name(issuer)
    .public_key(key.public_key())
    .serial_number(x509.random_serial_number())
    .not_valid_before(datetime.utcnow())
    .not_valid_after(datetime.utcnow() + timedelta(days=365))
    .sign(key, hashes.SHA256())
)

# Simpan sertifikat
with open("cert.pem", "wb") as f:
    f.write(cert.public_bytes(serialization.Encoding.PEM))

print("Sertifikat digital berhasil dibuat: cert.pem")

## 5. Hasil dan Pembahasan
(- Lampirkan screenshot hasil eksekusi program (taruh di folder `screenshots/`).  
- Berikan tabel atau ringkasan hasil uji jika diperlukan.  
- Jelaskan apakah hasil sesuai ekspektasi.  
- Bahas error (jika ada) dan solusinya. 

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](screenshots/kriptoweek10.png)

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
