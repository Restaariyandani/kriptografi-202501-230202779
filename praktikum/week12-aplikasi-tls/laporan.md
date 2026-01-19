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

## 3. Hasil dan Pembahasan
langkah 1 : Website Shopee:
1. Menggunakan HTTPS (TLS aktif)
2. Sertifikat valid dan masih berlaku
3. Diterbitkan oleh CA terpercaya
4. Menggunakan algoritma kriptografi kuat (SHA-256, TLS0
Langkah 2 Bagaimana enkripsi digunakan untuk melindungi transaksi online?
1. Pada aktivitas daring seperti proses masuk akun dan transaksi pembayaran, mekanisme TLS berperan menjaga kerahasiaan data dengan mengamankan jalur komunikasi antara peramban pengguuna dan server e-commerce. Pada saat autentikasi, kredensial berupa nama pengguna dan kata sandi dikodekan menggunakan kunci sesi simetris (contohnya AES) yang dihasilkan melalui tahapan TLS handshake. Sementara itu, pada fase pembayaran, informasi penting seperti nomor kartu, kode keamanan (CVV), serta rincian transaksi juga disandikan, sehingga hanya server yang dituju mampu menguraikannya, sedangkan pihak lain di dalam jaringan tidak dapat mengakses atau memahami data tersebut.

Potensi ancaman jika TLS tidak digunakan
1. Apabila TLS tidak digunakan, infromasi dikirimkan dalam fromat terbuka yang mudah dibaca, sehingga tingkat keamnanannya sangat rendah. Salah satu reiko terbesar adalah serangan Man-in-the-Middle (MITM), yaitu kondisi ketika [ihak tidak berwenang dapat mencegat, memodifikasi, atau mengambil data pengguna salama proses pengiriman. Selain itu, potensi ancaman lain mencangkup pengambil alihan akun, manipulasi transaksi, serta terbukanya informasi keuangan, yang pada akhirnya merugikan pengguna dan mengikis kepercayaan terhadap layanan e-commerce.

Langkah 3 Identifikasi isu privasi dalam penggunaan email terenkripsi (PGP, S/MIME
1. Teknologi ini menjaga kerahasiaan konten pesan, tetapi persoalan privasi tetap muncul terkait pengelolaan kunci serta keterbukaan metadata email yang masih bisa dianalisis. Dari sudut pandang etis, perusahaan hanya boleh mengakses dan membuka email karyawan untuk keperluan audit apabila dilakukan secara terbatas, terbuka, dan sesuai dengan kebijakan resmi, sehingga tidak melanggar hak privasi. Di sisi lain, pengawasan oleh pemerintah terhadap komunikasi yang dienkripsi perlu menyeimbangkan aspek keamanan dan perlindungan privasi melalui aturan yang jelas serta izin hukum yang sah, tanpa merusak kekuatan sistem enkripsi itu sendiri.
   ![Hasil Eksekusi](screenshots/kriptoweek12.png)

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
