# Tugas-OAK-24-03-2025

1. Jelaskan struktur antar hubungan dan beri contohnya.

= Struktur antar hubungan adalah pola keterkaitan antara berbagai elemen dalam suatu sistem, baik itu dalam organisasi, masyarakat, teknologi, maupun ekosistem. Hubungan ini bisa berbentuk hierarki (bertingkat), jaringan (terhubung tanpa tingkatan), atau hubungan timbal balik (saling memengaruhi).  

 Macam-macam Struktur Antar Hubungan & Contohnya  

1. Hierarki (Struktur Bertingkat)  
   Struktur ini memiliki tingkatan dengan hubungan dari atas ke bawah, di mana elemen yang lebih tinggi memiliki wewenang atau pengaruh lebih besar terhadap elemen di bawahnya.  
   - Contoh: Dalam perusahaan, CEO memimpin para manajer, manajer membawahi karyawan, dan karyawan menjalankan tugas yang diberikan.  

2. Jaringan (Interkoneksi Bebas)  
   Dalam struktur ini, elemen-elemen saling terhubung tanpa adanya tingkatan yang jelas, sehingga hubungan bersifat fleksibel dan lebih horizontal.  
   - Contoh: Media sosial seperti Facebook dan Instagram, di mana setiap pengguna bisa terhubung dengan siapa saja tanpa ada batasan tingkatan.  

3. Timbal Balik (Saling Memengaruhi)  
   Hubungan ini bersifat simetris, di mana setiap elemen saling memengaruhi dan memiliki ketergantungan satu sama lain.  
   - Contoh: Ekosistem, di mana tumbuhan menghasilkan oksigen bagi hewan dan manusia, sementara hewan menyediakan karbon dioksida yang dibutuhkan tumbuhan untuk fotosintesis.  

Struktur antar hubungan sangat penting dalam berbagai aspek kehidupan, karena membantu memahami bagaimana elemen-elemen dalam suatu sistem berinteraksi dan bekerja bersama untuk mencapai tujuan tertentu.

2. Bila terlalu banyak modul atau perangkat dihubungkan pada bus maka akan terjadi penurunan kinerja, sebutkan penyebabnya?

= Jika terlalu banyak modul atau perangkat dihubungkan pada bus, maka akan terjadi penurunan kinerja sistem karena beberapa alasan utama berikut:  

1. Kontensi (Contention) pada Bus  
   - Bus adalah jalur komunikasi yang digunakan oleh beberapa perangkat untuk bertukar data.  
   - Jika banyak perangkat ingin mengakses bus secara bersamaan, akan terjadi perebutan akses, sehingga beberapa perangkat harus menunggu giliran untuk mengirim atau menerima data.  
   - Hal ini menyebabkan bottleneck, di mana kinerja sistem menurun akibat keterlambatan akses.  

2. Bandwidth Terbatas  
   - Setiap bus memiliki kapasitas maksimal dalam mentransfer data (misalnya dalam satuan Mbps atau Gbps).  
   - Jika terlalu banyak perangkat berbagi bus yang sama, kecepatan transfer data untuk masing-masing perangkat akan berkurang karena mereka harus berbagi bandwidth yang ada.  
   - Contoh: Jika sebuah bus memiliki bandwidth 1 Gbps dan ada 10 perangkat aktif, maka rata-rata tiap perangkat hanya mendapat 100 Mbps (asumsi pembagian merata).  

3. Waktu Tunggu yang Meningkat (Latency)  
   - Karena banyak perangkat terhubung ke satu bus, waktu yang diperlukan untuk mendapatkan akses akan meningkat.  
   - Latensi terjadi karena setiap perangkat harus menunggu giliran untuk berkomunikasi dengan bus.  
   - Semakin banyak perangkat, semakin lama waktu tunggu, yang menyebabkan sistem menjadi lebih lambat.  

4. Overhead pada Manajemen Akses Bus  
   - Sistem harus mengatur siapa yang boleh menggunakan bus dan kapan waktunya.  
   - Teknik arbitrasi bus digunakan untuk mengelola akses, seperti:  
     - Polling (CPU mengecek perangkat satu per satu)  
     - Token Passing (giliran akses diberikan secara bergantian)  
     - Priority-based Access (perangkat dengan prioritas lebih tinggi mendapat akses lebih dulu)  
   - Semakin banyak perangkat, semakin kompleks manajemen aksesnya, yang bisa menambah beban kerja CPU dan memperlambat proses keseluruhan.  

5. Noise atau Interferensi Sinyal  
   - Semakin banyak perangkat yang terhubung, semakin besar kemungkinan terjadi interferensi sinyal listrik pada bus.  
   - Interferensi ini bisa menyebabkan error pada data atau memperlambat kecepatan komunikasi karena harus dilakukan koreksi data (error correction).  
   - Dalam sistem digital, hal ini bisa mengakibatkan keharusan untuk mengirim ulang data, yang menambah latensi dan menurunkan efisiensi komunikasi.  

Solusi untuk Mengatasi Masalah Ini  
1. Menggunakan Bus dengan Bandwidth Lebih Besar = Misalnya, mengganti bus lama dengan versi yang lebih cepat seperti PCIe dibandingkan PCI biasa.  
2. Menggunakan Multiple Bus = Memisahkan jalur bus untuk kelompok perangkat yang berbeda, seperti membedakan antara bus memori dan bus I/O.  
3. Menggunakan Arsitektur Point-to-Point = Seperti yang digunakan dalam PCI Express, di mana setiap perangkat memiliki jalur langsung ke prosesor tanpa berbagi bandwidth dengan perangkat lain.  
4. Menerapkan Teknik Buffering dan Caching = Untuk menyimpan data sementara dan mengurangi beban pada bus utama.  

Dengan memahami faktor-faktor di atas, sistem dapat dirancang dengan lebih efisien untuk menghindari kemacetan pada bus dan memastikan kinerja tetap optimal.

3. Umumnya perangkat berprioritas paling rendah memiliki waktu tunggu rata-rata yang paling singkat. Dengan dasar ini biasanya CPU diberi perioritas tertinggi pada SBI. Sebutkan alasan perangkat berprioritas 16 memiliki waktu tunggu rata-rata paling rendah? Dibawah kondisi seperti apa keadaan diatas tidak berlaku?

= Alasan Perangkat Berprioritas 16 Memiliki Waktu Tunggu Rata-Rata Paling Rendah  
Dalam SBI (System Bus Interface) atau sistem yang menggunakan prioritas akses bus, perangkat dengan **prioritas lebih tinggi** biasanya mendapatkan akses lebih dahulu dibandingkan perangkat dengan prioritas lebih rendah.  

Namun, jika prioritas diberikan dengan metode "Round Robin" atau sistem berbasis antrian, perangkat dengan prioritas paling rendah (misalnya, prioritas 16) sering kali memiliki waktu tunggu rata-rata lebih rendah dibandingkan perangkat dengan prioritas menengah.  

Mengapa demikian?  
1. Perangkat Prioritas Tertinggi Selalu Mendapat Akses Lebih Dulu  
   - Perangkat prioritas tinggi akan lebih sering diberikan akses lebih dulu.  
   - Tetapi, karena mereka sering mendapatkan akses, jumlah total antrian bisa lebih kecil untuk perangkat prioritas lebih rendah.  

2. Perangkat Prioritas Menengah Sering Terjebak dalam Antrian  
   - Perangkat dengan prioritas sedang seringkali mengalami blokade karena mereka harus menunggu perangkat prioritas tinggi terlebih dahulu, tetapi juga masih lebih cepat mendapat giliran dibanding perangkat prioritas paling rendah.  
   - Hal ini menyebabkan perangkat prioritas menengah sering kali memiliki waktu tunggu rata-rata yang lebih lama.  

3. Perangkat Prioritas Terendah Mendapat Akses Ketika Semua Perangkat Lain Selesai  
   - Karena perangkat prioritas rendah (misalnya, prioritas 16) hanya akan mengakses bus saat tidak ada perangkat lain yang lebih tinggi sedang membutuhkan akses, mereka sering kali mendapatkan slot kosong dengan cepat, sehingga waktu tunggunya lebih pendek daripada perangkat yang berada di tengah-tengah hirarki prioritas.  

---

Kondisi di Mana Keadaan Ini Tidak Berlaku  
Terdapat beberapa situasi di mana perangkat prioritas 16 tidak memiliki waktu tunggu rata-rata paling rendah:  

1. Jika Beban Kerja Perangkat Prioritas Tinggi Sangat Tinggi  
   - Jika perangkat berprioritas tinggi (1-15) terus-menerus menggunakan bus, perangkat prioritas 16 akan jarang sekali mendapatkan kesempatan** untuk mengakses bus.  
   - Dalam kondisi ini, perangkat prioritas 16 akan memiliki waktu tunggu yang jauh lebih lama dibandingkan perangkat lainnya.  

2. Jika Menggunakan Metode FIFO (First-In, First-Out)  
   - Dalam sistem yang menggunakan antrian FIFO (bukan berbasis prioritas), setiap perangkat akan dilayani berdasarkan urutan kedatangannya, bukan berdasarkan prioritasnya.  
   - Ini membuat semua perangkat memiliki waktu tunggu yang relatif sama, tidak tergantung pada prioritasnya.  

3. Jika Sistem Menggunakan Time-Slice atau Time-Sharing  
   - Dalam beberapa sistem, akses bus bisa diatur dengan metode time-sharing, di mana semua perangkat diberikan jatah waktu yang sama untuk mengakses bus tanpa memperhatikan prioritasnya.  
   - Ini akan menghilangkan keuntungan yang biasanya dimiliki perangkat prioritas rendah.  

4. Jika Ada Starvation (Kelaparan Sumber Daya)  
   - Jika sistem tidak memiliki mekanisme fair scheduling, perangkat berprioritas rendah bisa saja tidak pernah mendapatkan akses bus karena selalu kalah dari perangkat dengan prioritas lebih tinggi.  
   - Akibatnya, perangkat dengan prioritas 16 bisa memiliki waktu tunggu yang sangat panjang atau bahkan tidak mendapat akses sama sekali.  

---

Kesimpulan  
- Dalam sistem berbasis antrian dengan metode Round Robin atau sistem prioritas tertentu, perangkat prioritas 16 sering memiliki waktu tunggu rata-rata paling rendah karena hanya perlu menunggu sampai semua perangkat dengan prioritas lebih tinggi selesai.  
- Namun, dalam kondisi beban tinggi, FIFO, time-sharing, atau sistem tanpa fair scheduling, aturan ini tidak berlaku, dan perangkat prioritas rendah bisa mengalami waktu tunggu yang lebih lama.
