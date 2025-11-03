# Laporan Praktikum Kriptografi
Minggu ke-: 4  
Topik: Entropy & Unicity Distance (Evaluasi Kekuatan Kunci dan Brute Force)  
Nama: Resta Ariyandani  
NIM: 230202779 
Kelas: 5IKRA 

---

## 1. Tujuan
Menyelesaikan perhitungan sederhana terkait entropi kunci, Menggunakan teorema Euler pada contoh perhitungan modular & invers, Menghitung unicity distance untuk ciphertext tertentu, Menganalisis kekuatan kunci berdasarkan entropi dan unicity distance, Mengevaluasi potensi serangan brute force pada kriptosistem sederhana.


## 2. Dasar Teori
Entropi menggambarkan tingkat ketidakpastian atau keacakan dalam suatu sistem. Secara sederhana, entropi menunjukkan seberapa sulit sebuah sistem diprediksi atau seberapa acak komponennya. Semakin tinggi nilai entropi, semakin besar tingkat ketidakteraturan dan semakin sulit sistem tersebut diperkirakan. Dalam konteks informasi, entropi menunjukkan jumlah rata-rata bit yang dibutuhkan untuk merepresentasikan suatu data atau kunci secara unik. Entropi sering dihitung menggunakan rumus dari Claude Shannon (1948): H(X)=−i=1∑pi​ log2 ​pi​

Makna Entropi dalam Kriptografi sendiri yaitu entropi menggambarkan seberapa acak dan tidak terduganya suatu kunci enkripsi; semakin tinggi nilai entropinya, semakin sulit kunci tersebut diprediksi atau dibobol, sehingga sistem menjadi lebih aman terhadap serangan.

Keterkaitan dengan Brute Force
Serangan brute-force bekerja dengan mencoba setiap kemungkinan kunci sampai yang benar ditemukan. Jumlah kombinasi yang harus diuji tumbuh eksponensial terhadap entropi: N=2H Semakin besar 𝐻, ruang kunci menjadi jauh lebih luas sehingga waktu dan usaha untuk menebak kunci secara brute-force meningkat secara drastis.

Unicity Distance (UD) dalam kriptografi adalah ukuran yang menunjukkan jumlah minimum ciphertext yang diperlukan untuk dapat menentukan kunci enkripsi secara pasti dan tanpa ambiguitas; semakin besar nilai UD, semakin banyak data yang harus dikumpulkan oleh penyerang untuk memecahkan sistem, sehingga tingkat keamanan algoritma enkripsi menjadi lebih tinggi.
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
1. Apa arti dari nilai entropy dalam konteks kekuatan kunci? Jawab: Dalam konteks keamanan kunci, entropi merepresentasikan tingkat acak dan tidak terduganya suatu kunci enkripsi. Nilai entropi yang tinggi menandakan semakin banyak kemungkinan kombinasi kunci yang bisa terbentuk, sehingga kunci tersebut lebih sulit diprediksi atau dibobol. Dengan demikian, semakin besar entropi, semakin kuat dan aman sistem kriptografi terhadap berbagai bentuk serangan, terutama brute force.
2. Mengapa unicity distance penting dalam menentukan keamanan suatu cipher? Jawab: Unicity distance penting karena menunjukkan seberapa banyak ciphertext yang dibutuhkan untuk menebak kunci dengan pasti; semakin besar nilainya, semakin aman cipher dari serangan.
3. Mengapa brute force masih menjadi ancaman meskipun algoritma sudah kuat? Jawab: Brute force masih dianggap berbahaya meskipun algoritma kriptografi sudah kuat karena serangan ini tidak bergantung pada kelemahan algoritma, melainkan menguji setiap kemungkinan kunci hingga menemukan yang benar. Jika panjang kunci atau tingkat entropinya rendah, penyerang dengan kemampuan komputasi tinggi tetap dapat memecahkannya. Selain itu, kemajuan teknologi, termasuk komputasi kuantum, dapat mempercepat proses pencarian kunci, sehingga brute force tetap menjadi ancaman nyata bagi sistem enkripsi. 

## 7. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
