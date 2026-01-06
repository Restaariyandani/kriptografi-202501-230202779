# Laporan Praktikum Kriptografi
Minggu ke-: 6  
Topik: Cipher Modern (DES, AES, RSA)  
Nama: Resta Ariyandani  
NIM: 230202779
Kelas: 5IKRA  

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

1. Mengimplementasikan algoritma DES untuk blok data sederhana.
2. Menerapkan algoritma AES dengan panjang kunci 128 bit.
3. Menjelaskan proses pembangkitan kunci publik dan privat pada algoritma RSA.

## 2. Dasar Teori
1. DES (Data Encryption Standard) adalah metode enkripsi simetris yang digunakan       untuk mengamankan data dengan satu kunci yang sama, bekerja dengan                 mengenkripsi data dalam blok berukuran 64 bit dan menggunakan kunci sepanjang      56 bit. Metode ini dulu banyak dipakai, tetapi sekarang sudah tidak                direkomendasikan karena tingkat keamanannya rendah.
2. AES (Advanced Encryption Standard) adalah metode enkripsi yang digunakan untuk     menjaga keamanan data dengan mengacak informasi agar tidak bisa dibaca             sembarang orang. AES memakai satu kunci yang sama untuk mengunci dan membuka       data, serta dikenal aman dan cepat. Karena keandalannya, AES banyak digunakan      dalam sistem keamanan modern seperti aplikasi, jaringan, dan penyimpanan data.
3. RSA (Rivest–Shamir–Adleman) adalah teknik enkripsi yang menjaga keamanan data      dengan menggunakan dua kunci berbeda, yaitu kunci publik dan kunci privat. Data    dikunci dengan kunci publik dan hanya bisa dibuka dengan kunci privat. Cara ini    membuat RSA banyak digunakan untuk mengamankan komunikasi dan pertukaran data      secara aman di dunia digital.

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )
  

## 5. Source Code
from Crypto.Cipher import DES
from Crypto.Random import get_random_bytes

key = get_random_bytes(8)  # kunci 64 bit (8 byte)
cipher = DES.new(key, DES.MODE_ECB)

plaintext = b"ABCDEFGH"
ciphertext = cipher.encrypt(plaintext)
print("Ciphertext:", ciphertext)

decipher = DES.new(key, DES.MODE_ECB)
decrypted = decipher.decrypt(ciphertext)
print("Decrypted:", decrypted)
from Crypto.Cipher import AES
from Crypto.Random import get_random_bytes

key = get_random_bytes(16)  # 128 bit key
cipher = AES.new(key, AES.MODE_EAX)

plaintext = b"Modern Cipher AES Example"
ciphertext, tag = cipher.encrypt_and_digest(plaintext)

print("Ciphertext:", ciphertext)

# Dekripsi
cipher_dec = AES.new(key, AES.MODE_EAX, nonce=cipher.nonce)
decrypted = cipher_dec.decrypt(ciphertext)
print("Decrypted:", decrypted.decode())
from Crypto.PublicKey import RSA
from Crypto.Cipher import PKCS1_OAEP

# Generate key pair
key = RSA.generate(2048)
private_key = key
public_key = key.publickey()

# Enkripsi dengan public key
cipher_rsa = PKCS1_OAEP.new(public_key)
plaintext = b"RSA Example"
ciphertext = cipher_rsa.encrypt(plaintext)
print("Ciphertext:", ciphertext)

# Dekripsi dengan private key
decipher_rsa = PKCS1_OAEP.new(private_key)
decrypted = decipher_rsa.decrypt(ciphertext)
print("Decrypted:", decrypted.decode())



## 6. Hasil dan Pembahasan


![Hasil Eksekusi](screenshots/kriptoweek6.png)


---

## 7. Jawaban Pertanyaan
1. Apa perbedaan mendasar antara DES, AES, dan RSA dalam hal kunci dan keamanan?
   Jawab :
    > DES (Data Encryption Standard) adalah enkripsi simetris dengan satu kunci,         namun keamanannya rendah karena kunci pendek dan sudah tidak                       direkomendasikan.
    > AES (Advanced Encryption Standard) merupakan enkripsi simetris dengan              tingkat keamanan tinggi karena menggunakan kunci yang lebih panjang dan            masih banyak digunakan hingga saat ini.
    > RSA (Rivest–Shamir–Adleman) adalah enkripsi asimetris yang memakai kunci           publik dan privat, aman untuk pertukaran data meskipun prosesnya lebih             lambat dibanding AES.
2. Mengapa AES lebih banyak digunakan dibanding DES di era modern?
   Jawab :
   AES lebih banyak digunakan dibanding DES di era modern karena tingkat              keamanannya jauh lebih tinggi. DES memiliki kunci yang pendek sehingga mudah       ditembus oleh teknologi saat ini, sedangkan AES menggunakan kunci yang lebih       panjang dan kuat sehingga lebih aman dari serangan. Selain itu, AES juga lebih     efisien dan cepat digunakan pada berbagai perangkat dan sistem, sehingga           menjadi standar utama untuk keamanan data modern.
4. Mengapa RSA dikategorikan sebagai algoritma asimetris, dan bagaimana proses        pembangkitan kuncinya?
   Jawab :
   RSA disebut algoritma asimetris karena menggunakan dua kunci berbeda, yaitu        kunci publik untuk mengenkripsi data dan kunci privat untuk membukanya. Kunci      RSA dibuat dengan memilih dua bilangan prima besar lalu melakukan perhitungan      matematika untuk menghasilkan pasangan kunci yang saling terkait. Keamanannya      bergantung pada sulitnya memecah bilangan besar tersebut.
   
## 8. Kesimpulan

Program kriptografi yang diimplementasikan menggunakan algoritma DES, AES, dan RSA berhasil menunjukkan proses enkripsi dan dekripsi data secara benar. DES sebagai algoritma simetris mampu mengamankan data sederhana, namun memiliki keterbatasan dari sisi keamanan. AES memberikan tingkat keamanan yang lebih tinggi dan sesuai untuk penggunaan modern, sedangkan RSA sebagai algoritma asimetris efektif digunakan dalam proses pertukaran kunci melalui mekanisme kunci publik dan privat. Hasil ini membuktikan bahwa penerapan kombinasi kriptografi simetris dan asimetris dapat meningkatkan keamanan data dalam sistem informasi. 
---



## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit week6-cipher-modern
Author: Resta ariyandani <restaariandani@gmail.com>
Date:   2026-01-05

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
