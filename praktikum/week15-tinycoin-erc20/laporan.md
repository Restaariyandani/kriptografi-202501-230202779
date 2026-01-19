# Laporan Praktikum Kriptografi
Minggu ke-: 15  
Topik: Tinycoin  
Nama: Resta Ariyandani 
NIM: 230202779  
Kelas: 5IKRA  

---

## 1. Tujuan
Mengembangkan proyek sederhana berbasis algoritma kriptografi. Mendokumentasikan proses implementasi proyek ke dalam repository Git. Menyusun laporan teknis hasil proyek akhir.

---

## 2. Dasar Teori
ERC-20 adalah pedoman teknis untuk pembuatan token di jaringan Ethereum yang menetapkan aturan umum agar berbagai aplikasi dapat mengenali dan menggunakan token dengan cara yang sama. Melalui standar ini, dompet digital, platform perdagangan, dan kontrak pintar lain bisa berkomunikasi dengan token tanpa perlu penyesuaian khusus. Di dalamnya sudah ditetapkan fungsi inti, seperti melihat jumlah token yang dimiliki, memindahkan token ke alamat lain, serta memberikan izin kepada pihak tertentu untuk menggunakan token atas nama pemilik.

---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---

## 5. Source Code
(Salin kode program utama yang dibuat atau dimodifikasi.  
Gunakan blok kode:

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract TinyCoin is ERC20 {
    constructor(uint256 initialSupply) ERC20("TinyCoin", "TNC") {
        _mint(msg.sender, initialSupply);
    }
}

---

## 6. Hasil dan Pembahasan
Kontrak pintar TinyCoin berhasil dibuat dan dijalankan melalui Remix IDE tanpa ditemukan kesalahan saat proses kompilasi. Setelah itu, kontrak dipasang pada lingkungan JavaScript VM atau jaringan uji Ethereum, dan sistem memberikan alamat khusus yang menjadi penanda resmi TinyCoin di dalam blockchain. Keberhasilan proses ini menandakan bahwa rancangan token sudah mengikuti ketentuan ERC-20 dan dapat dioperasikan sebagaimana mestinya.

Pengujian terhadap fungsi balanceOf(address) memperlihatkan bahwa jumlah token awal sudah tercatat dengan benar pada alamat pemilik sesuai dengan nilai suplai yang ditetapkan. Sementara itu, percobaan menggunakan fungsi transfer(address, amount) menunjukkan bahwa token dapat berpindah antar alamat, di mana saldo pengirim berkurang dan saldo penerima bertambah sesuai dengan nilai yang dikirimkan.

Selain itu, pemeriksaan setelah transaksi memastikan bahwa total token yang beredar tidak berubah. Temuan ini menguatkan bahwa mekanisme pemindahan dalam kontrak tidak menambah atau mengurangi jumlah token secara tidak sah, sehingga keandalan dan konsistensi sistem TinyCoin tetap terjaga.

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](screenshots/kriptoweek15.png)
)

---

## 7. Jawaban Pertanyaan
 1. Apa fungsi utama ERC20 dalam ekosistem blockchain?
    jawab:
    Peran utama ERC-20 adalah menjadi pedoman umum bagi pembuatan token di             jaringan Ethereum agar semua aplikasi bisa berinteraksi dengan cara yang sama.     Dengan aturan ini, dompet, platform perdagangan, dan kontrak lain dapat            mengenali serta menggunakan token tanpa perlu penyesuaian khusus. Hasilnya,        fungsi dasar seperti melihat saldo, mengirim token, dan memberi izin               penggunaan oleh pihak tertentu dapat berjalan lebih lancar dan konsisten.
2. Bagaimana mekanisme transfer token bekerja dalam kontrak ERC20?
   jawab:
   Dalam kontrak ERC-20, pemindahan token terjadi ketika pemilik token memanggil      fungsi transfer dan menentukan alamat tujuan serta jumlah yang ingin dikirim.      Sistem kemudian memeriksa apakah saldo pengirim mencukupi. Jika memenuhi,          kontrak akan mengurangi saldo pengirim dan menambahkan jumlah yang sama ke         saldo penerima. Setiap proses ini dicatat di blockchain melalui event, sehingga    pergerakan token dapat dilacak dan diverifikasi oleh siapa pun di jaringan.
3. Apa risiko utama dalam implementasi smart contract dan bagaimana cara              mitigasinya?
   jawab:
   Risiko terbesar dalam penerapan smart contract biasanya berasal dari kesalahan     penulisan kode, celah keamanan, atau pengaturan yang kurang tepat, yang bisa       dimanfaatkan untuk mencuri aset atau merusak fungsi kontrak. Masalah seperti       bug logika, serangan reentrancy, dan penggunaan pustaka yang sudah usang sering    menjadi pintu masuk bagi penyerang. Untuk menguranginya, pengembang perlu          melakukan pengujian menyeluruh, audit keamanan oleh pihak independen, serta        menerapkan praktik pengembangan yang baik, seperti penggunaan standar tepercaya    dan pembaruan sistem secara berkala.

---


## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit 
Author: Resta <restaariandani@gmail.com>
Date:   2026-01-20

   week15-tinycoin-erc20
```
