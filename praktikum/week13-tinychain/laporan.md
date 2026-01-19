# Laporan Praktikum Kriptografi
Minggu ke-: 13  
Topik:Tiny chain POW  
Nama: Resta Ariyandani 
NIM: 230202779  
Kelas: 5IKRA 

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

Menjelaskan peran hash function dalam blockchain.
Melakukan simulasi sederhana Proof of Work (PoW).
Menganalisis keamanan cryptocurrency berbasis kriptografi.


## 2. Dasar Teori
Dalam teknologi blockchain, setiap blok diberi semacam identitas digital yang dihasilkan oleh fungsi hash. Identitas ini sangat peka terhadap perubahan, sehingga jika ada sedikit saja data yang diubah, nilai hash akan langsung berbeda dan upaya manipulasi bisa segera diketahui.

Sementara itu, Proof of Work (PoW) digunakan sebagai cara jaringan mencapai kesepakatan, di mana penambang harus mencoba berbagai nilai nonce hingga menemukan hash yang sesuai dengan tingkat kesulitan yang ditentukan. Karena proses ini membutuhkan banyak perhitungan, pemalsuan blok menjadi sulit dan memakan sumber daya besar.

Keamanan pada sistem cryptocurrency dibangun dari gabungan teknik hashing, kriptografi kunci publik, dan mekanisme PoW. Jika seseorang ingin mengubah data, ia harus menghitung ulang seluruh blok setelahnya, yang dalam praktik hampir tidak mungkin dilakukan karena besarnya beban komputasi yang dibutuhkan.
## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---

## 5. Source Code
(Salin kode program utama yang dibuat atau dimodifikasi.  
Gunakan blok kode:

import hashlib
import time

class Block:
    def __init__(self, index, previous_hash, data, timestamp=None):
        self.index = index
        self.timestamp = timestamp or time.time()
        self.data = data
        self.previous_hash = previous_hash
        self.nonce = 0
        self.hash = self.calculate_hash()

    def calculate_hash(self):
        value = str(self.index) + str(self.timestamp) + str(self.data) + str(self.previous_hash) + str(self.nonce)
        return hashlib.sha256(value.encode()).hexdigest()

    def mine_block(self, difficulty):
        while self.hash[:difficulty] != "0" * difficulty:
            self.nonce += 1
            self.hash = self.calculate_hash()
        print(f"Block mined: {self.hash}")
        
class Blockchain:
    def __init__(self):
        self.chain = [self.create_genesis_block()]
        self.difficulty = 4

    def create_genesis_block(self):
        return Block(0, "0", "Genesis Block")

    def get_latest_block(self):
        return self.chain[-1]

    def add_block(self, new_block):
        new_block.previous_hash = self.get_latest_block().hash
        new_block.mine_block(self.difficulty)
        self.chain.append(new_block)

# Uji coba blockchain
my_chain = Blockchain()
print("Mining block 1...")
my_chain.add_block(Block(1, "", "Transaksi A → B: 10 Coin"))

print("Mining block 2...")
my_chain.add_block(Block(2, "", "Transaksi B → C: 5 Coin"))
    

## 6. Hasil dan Pembahasan
Hasil uji coba proses penambangan pada TinyChain memperlihatkan bahwa durasi penambangan tidak bersifat konstan, melainkan dipengaruhi langsung oleh tingkat kesulitan yang digunakan. Ketika parameter kesulitan berada pada level rendah, sistem dapat dengan cepat menemukan nilai acak (nonce) yang menghasilkan pola hash sesuai ketentuan. Namun, saat ambang kesulitan dinalikkan, jumlah percobaan yang harus dilakukan meningkat drastis, sehingga waktu yang dibutuhkan untuk menyelesaikan proses tersebut menjadi jaluh lebih panjang.
Temuan ini menegakan adanya hubungan searah antara besarnya nilai difficulty dan lamanya proses mining. Semakin ketat persyaratan hash yang ditetapkan, semakin kecil peluang sistem memperoleh hasil yang valid dalam setiap percobaan, sehingga durasi komputasi pun bertambah.
Pola kerja ini berperan sebagain lapisan bagi blockchain, karena pihak yang berniat merusak atau mengubah data harus menge;uarkan daya komputasi serta waktu yang sangat besar, Akibatnya, upaya seperti pemalsuan transaksi atau pengeluaran ganda menjadi tidak ekonomis, sekaligus mempertahankan keandalan dan keutuhan data dalam jaringan blockchain.

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](screenshots/kriptoweek13.png)


## 7. Jawaban Pertanyaan
1. Mengapa fungsi hash sangat penting dalam blockchain?
   jawab:
   Fungsi hash berperan penting dalam blockchain karena digunakan untuk menjaga      keaslian dan keterkaitan data antarblok. Setiap perubahan kecil pada isi blok     akan menghasilkan nilai hash yang berbeda, sehingga manipulasi dapat dengan       mudah terdeteksi. Selain itu, hash juga dimanfaatkan dalam proses pembuatan       blok baru agar tidak bisa dilakukan secara sembarangan, sehingga sistem tetap     aman dan dapat dipercaya.
2. Bagaimana Proof of Work mencegah double spending?
   jawab:
   Proof of Work mencegah double spending dengan memastikan setiap transaksi         harus melewati proses perhitungan yang memakan waktu sebelum bisa dicatat         dalam blockchain. Setelah sebuah blok ditambahkan dan terhubung dengan blok       sebelumnya, data di dalamnya menjadi sulit diubah. Jika ada yang mencoba          memakai koin yang sama dua kali, ia harus menghitung ulang seluruh blok           berikutnya untuk menyaingi rantai yang sudah diakui jaringan, yang membutuhkan    sumber daya sangat besar.
3. Apa kelemahan dari PoW dalam hal efisiensi energi?
   jawab:
   Kelemahan utama Proof of Work dalam hal efisiensi energi adalah kebutuhan daya    listrik yang sangat besar karena proses penambangan mengharuskan banyak           perangkat melakukan perhitungan berulang-ulang untuk menemukan hash yang          sesuai. Sebagian besar upaya komputasi tersebut tidak menghasilkan blok baru,     sehingga energi yang digunakan sering kali terbuang. Akibatnya, PoW dinilai       kurang ramah lingkungan dan memiliki biaya operasional yang tinggi                dibandingkan dengan mekanisme konsensus lain.
  

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit 
Author: Resta <restaariandani@gmail.com>
Date:   2026-01-19

    week13-tinychain
```
