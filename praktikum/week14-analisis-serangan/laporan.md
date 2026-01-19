# Laporan Praktikum Kriptografi
Minggu ke-: 14  
Topik:  analisis serangan 
Nama: Resta Ariyandani  
NIM: 230202779  
Kelas: 5IKRA  

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

Mengidentifikasi jenis serangan pada sistem informasi nyata.
Mengevaluasi kelemahan algoritma kriptografi yang digunakan.
Memberikan rekomendasi algoritma kriptografi yang sesuai untuk perbaikan keamanan.

---

## 2. Dasar Teori
Kriptografi pada dasarnya berfungsi sebagai “pengaman” informasi, sehingga data hanya bisa dibaca atau digunakan oleh pihak yang memang memiliki hak akses. Dalam praktik sistem digital saat ini, teknik ini dimanfaatkan untuk memastikan data tetap bersifat rahasia, tidak berubah selama dikirim atau disimpan, serta benar-benar berasal dari sumber yang sah. Hal tersebut dicapai melalui penerapan berbagai metode, seperti pemakaian kunci rahasia dan kunci publik, serta perhitungan nilai hash. Namun, tingkat keamanan tidak hanya ditentukan oleh kecanggihan metode yang dipilih, melainkan juga oleh ketepatan penerapan dan pengaturan sistemnya.
Banyak celah keamanan muncul bukan semata karena teknik kriptografinya lemah, tetapi karena penggunaan standar lama atau pengaturan yang kurang tepat. Serangan seperti menebak sandi secara berulang, penyadapan di tengah jalur komunikasi, atau pengiriman ulang data yang sudah pernah dikirim sering kali terjadi dalam kondisi tersebut. Sebagai contoh, algoritma lama seperti MD5 dan SHA-1 tidak lagi cocok untuk menyimpan kata sandi karena dapat diproses terlalu cepat oleh komputer modern. Hal serupa juga berlaku pada penggunaan versi TLS yang sudah usang, yang membuat komunikasi lebih mudah diintip oleh pihak tidak bertanggung jawab.

---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `caesar_cipher.py` di folder `praktikum/week2-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)

---

## 5. Source Code
(Salin kode program utama yang dibuat atau dimodifikasi.  
Gunakan blok kode:
import hashlib
import itertools
import string
import time

# ===== Konfigurasi target (simulasi) =====
password_asli = "ab1"  # password lemah & pendek
target_hash = hashlib.sha256(password_asli.encode()).hexdigest()

print("Target hash:", target_hash)

# ===== Parameter brute force =====
karakter = string.ascii_lowercase + string.digits  # a-z + 0-9
panjang_maks = 3

start = time.time()
percobaan = 0
ketemu = False

# ===== Proses brute force =====
for panjang in range(1, panjang_maks + 1):
    for kombinasi in itertools.product(karakter, repeat=panjang):
        tebakan = ''.join(kombinasi)
        hash_tebakan = hashlib.sha256(tebakan.encode()).hexdigest()
        percobaan += 1

        if hash_tebakan == target_hash:
            print("\nPassword ditemukan!")
            print("Password :", tebakan)
            print("Percobaan:", percobaan)
            ketemu = True
            break
    if ketemu:
        break

end = time.time()
print("Waktu eksekusi:", round(end - start, 3), "detik")

---

## 6. Hasil dan Pembahasan
Pada tahun 2016, LinkedIn kembali menjadi perhatian setelah terungkap bahwa jutaan data akun penggunanya beredar di internet. Lebih dari enam juta kata sandi diketahui dapat diakses oleh pihak luar karena sistem penyimpanan saat itu masih menggunakan hash SHA-1 tanpa salt, sehingga mudah dipecahkan dengan teknik seperti rainbow table dan percobaan otomatis.

Akses ilegal ke basis data menjadi jalur utama serangan tersebut. Permasalahan utamanya terletak pada pemilihan dan penerapan metode pengamanan yang kurang tepat, seperti penggunaan algoritma yang sudah tidak direkomendasikan serta tidak adanya perlindungan tambahan untuk membatasi upaya masuk berulang.

Untuk meningkatkan keamanan, sistem modern umumnya beralih ke algoritma khusus penyimpanan kata sandi seperti bcrypt, scrypt, atau Argon2 yang dirancang lebih lambat dan boros memori. Pendekatan ini membuat serangan brute force menjadi jauh lebih mahal dan memperkuat perlindungan akun meskipun terjadi kebocoran data.

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](screenshots/kriptoweek14.png)


---

## 7. Jawaban Pertanyaan
1. Mengapa banyak sistem lama masih rentan terhadap brute force atau dictionary      attack?
   jawab:
   Banyak sistem lama masih rentan terhadap brute force dan dictionary attack        karena menggunakan metode penyimpanan kata sandi yang sudah ketinggalan zaman.    Umumnya, hash yang dipakai bersifat cepat dan tidak dilengkapi salt atau          pembatasan percobaan masuk, sehingga penyerang dapat mencoba banyak kombinasi     dalam waktu singkat. Kurangnya pembaruan dan pengaturan keamanan yang memadai     juga membuat celah tersebut tetap terbuka.
2. Apa bedanya kelemahan algoritma dengan kelemahan implementasi?
   jawab:
   Perbedaan antara kelemahan algoritma dan kelemahan implementasi terletak pada     sumber masalahnya. Kelemahan algoritma berasal dari desain atau sifat dasar       algoritma itu sendiri, misalnya ketika suatu metode kriptografi terbukti          memiliki celah matematis atau tidak lagi cukup kuat menghadapi kemampuan          komputasi modern. Sementara itu, kelemahan implementasi muncul karena cara        algoritma tersebut diterapkan di dalam sistem, seperti penggunaan konfigurasi     yang salah, pengelolaan kunci yang buruk, atau pengamanan tambahan yang tidak     dipasang. Dengan kata lain, algoritma bisa saja kuat, tetapi jika diterapkan      secara keliru, sistem tetap menjadi tidak aman.
3. Bagaimana organisasi dapat memastikan sistem kriptografi mereka tetap aman di     masa depan?
   jawab:
   Organisasi dapat menjaga sistem kriptografinya tetap aman dengan rutin            memperbarui standar dan teknologi yang digunakan seiring berkembangnya ancaman    dan kemampuan komputasi. Pemilihan algoritma modern yang direkomendasikan,        disertai penerapan konfigurasi yang tepat, menjadi langkah dasar yang penting.    Selain itu, melakukan audit keamanan secara berkala, menguji sistem terhadap      skenario serangan terbaru, serta melatih tim teknis agar memahami praktik         terbaik juga membantu memastikan perlindungan data tetap kuat dalam jangka        panjang.


## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit 
Author: Resta <restaariandani@gmail.com>
Date:   2026-01-20

    week14-analisis-serangan
```
