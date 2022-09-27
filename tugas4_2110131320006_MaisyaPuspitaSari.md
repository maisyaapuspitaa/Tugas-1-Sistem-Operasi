Nama : Maisya Puspita Sari
NIM : 2110131320006
Tugas : Tugas 4 Perbedaan Struktur Sistem Operasi Sederhana, Berlapis dan Mikrokernel
______

### 1. Struktur Sederhana

<p align = "justify"> Sistem monolitik merupakan struktur sistem operasi sederhana yang dilengkapi dengan operasi “dual” pelayanan {sistem call} yang diberikan oleh sistem operasi. <b>Model sistem call dilakukan dengan cara mengambil sejumlah parameter pada tempat yang telah ditentukan sebelumnya, seperti register atau stack dan kemudian mengeksekusi suatu intruksi trap tertentu pada monitor mod</b>. Pada model ini, tiap-tiap sistem call memiliki satu service procedure. Utility procedure mengerjakan segala sesuatu yang dibutuhkan oleh beberapa service procedure, seperti mengambil data dari user program.</p>

Mekanisme dan prinsip kerja model struktur monolitik sistem operasi ini adalah sebagai berikut:

1. User program melakukan “trap” pada karnel
2. Intruksi berpindah dari user mode ke monitor mode dan mentransfer control ke sistem operasi.
3. Sistem operasi mengecek parameter — parameter dari pemanggilan tersebut, untuk menentukan sistem call mana yang memanggil.
4. Sistem operasi menunjuk ke suatu table yang berisi slot ke-k yang menunjuk sistem call K (Kontrol).
5. Kontrol akan dikembalikan kepada user program, jika sistem call telah selesai mengerjakan tugasnya.

<p align = "center"> <img src = "struktursederhana.png">
Penjelasan lapisan gambar di atas</p>

a. *Main Procedure* adalah suatu program yang digunakan untuk memanggil salah satu dari service prosedures, dan juga meminta pelayanan dari service procedures.

b. *Service Prosedures* adalah program yang diginakan untuk menjalankan fungsi pemanggilan procedures yang mana procedures itu harus di aktifkan.

c. *Utility Procedures* adalah program dasar yang digunakan untuk mengendalikan sistem komputer dan juga untuk mengerjakan apa yang dibutuhkan oleh service procedures.

### 2. Sistem Berlapis
<p align = "justify"> Teknik pendekatan struktur sistem berlapis sistem operasi pada dasarnya dibuat menggunakan <b>pendekatan top-down</b>, semua fungsi ditentukan dan dibagi menjadi komponen komponen. Modularisasi sistem dilakukan dengan cara memecah sistem operasi menajdi beberapa lapis (tingkat). Lapisan terendah (layer 0) adalah perangkat keras dan lapisan teratas (layer N) adalah user interface. <b>Dengan system modularisasi, setiap lapisan mempunyai fungsi (operasi) tertentu dan melayani lapisan yang lebih rendah</b>.</p>

<p align = "justify"> System operasi pertama kali yang memakai system berlapis adalah THE. System operasi THE yang dibuat oleh Dijkstra dan mahasiswa-mahasiswanya. Pada dasarnya system operasi berlapis dimaksudkan untuk mengurangi kompleknya rancangan dan implementasi dari suatu system operasi. Contoh sistem operasi yang menggunakan sistem ini adalah: UNIX termodifikasi, THE, Venus dan OS/2..</p>

<p align = "center"><img src = "strukturberlapis.png"></p>

* Lapisan 1. Berisi berbagai sirkuit elektronik, misal register, memory cells, dan logic gate.
* Lapisan 2. Berisi instruksi prosesor, misal instruksi aritmatika, instruksi transfer data, dsb.
* Lapisan 3. Penambahan konsep seperti prosedur/subrutin, maupun fungsi yang me-return nilai tertentu.
* Lapisan 4. Penambahan interrupt.
* Lapisan 5. Program sebagai sekumpulan instruksi yang dijalankan oleh prosesor.
* Lapisan 6. Berhubungan dengan secondary storage device, yaitu membaca/menulis head, track, dan sektor.
* Lapisan 7. Menciptakan alamat logika untuk proses. Mengatur hubungan antara main memory,virtual memory, dan secondary memory.
* Lapisan 8. Program sebagai sekumpulan instruksi yang dijalankan oleh prosesor.
* Lapisan 9. Berhubungan dengan secondary storage device, yaitu membaca/menulis head,track, dan sektor.
* Lapisan 10. Menciptakan alamat logika untuk proses. Mengatur hubungan antara main memory, virtual memory, dan secondary memory.
* Lapisan 11. Program sebagai sekumpulan instruksi yang dijalankan oleh prosesor
* Lapisan 12. File adalah objek yang memiliki nama dan ukuran. Abstraksi dari lapisan 9
* Lapisan 13. Menyediakan interface agar bisa berinteraksi dengan pengguna.

### 3. Struktur Mikrokernel

<p align = "justify"> Metode struktur ini adalah menghilangkan komponen-komponen yang tidak diperlukan dari kernel dan mengimplementasikannya sebagai sistem dan program-program level user. Hal ini akan menghasilkan kernel yang kecil. <b>Fungsi utama dari jenis ini adalah menyediakan fasilitas komunikasi antara program client dan bermacam pelayanan yang berjalan pada ruang user.</b></p>


<p align = "justify"> Sistem operasi yang menggunakan micro kernel umumnya secara dramatis memiliki kinerja di bawah kinerja sistem operasi yang menggunakan monolithic kernel. Hal ini disebabkan oleh adanya overhead yang terjadi akibat proses input/output dalam kernel yang ditujukan untuk mengganti konteks (context switch) untuk memindahkan data antara aplikasi dan server.</p>


<p align = "justify">Dalam teorinya, sistem operasi yang menggunakan microkernel dinamakan jauh bertambah stabil dibandingkan dengan monolithic kernel, karena sebuah server yang gagal memperagakan pekerjaan, tidak akan menyebabkan kernel dijadikan tidak bisa berlanjut, dan server tersebut akan dihentikan oleh kernel utama. Akan tetapi, dalam prakteknya, anggota dari system state bisa hilang oleh server yang gagal memperagakan pekerjaan tersebut, dan biasanya untuk memperagakan anggota eksekusi aplikasi pun dijadikan sulit, atau bahkan untuk menjalankan server-server lainnya.</p>

Contoh Sistem operasi yang menggunakan struktur ini adalah : TRU64 UNIX, MacOSX dan QNX.

<img src = "kernel.png">

______
<p align = "justify"> Sehingga dapat disimpulkan bahwasanya perbedaan struktur sistem operasi sederhana, berlapis, dan mikrokernel yaitu, struktur sederhana dilakukan dengan cara ;</p>

1. User program melakukan “trap” pada karnel
2. Intruksi berpindah dari user mode ke monitor mode dan mentransfer control ke sistem operasi.
3. Sistem operasi mengecek parameter — parameter dari pemanggilan tersebut, untuk menentukan sistem call mana yang memanggil.
4. Sistem operasi menunjuk ke suatu table yang berisi slot ke-k yang menunjuk sistem call K (Kontrol).
5. Kontrol akan dikembalikan kepada user program, jika sistem call telah selesai mengerjakan tugasnya.

<p align = "justify">Sedangkan pada sistem berlapis dilakukan dengan metode <i>top-down</i> yaitu dengan system modularisasi, setiap lapisan mempunyai fungsi (operasi) tertentu dan melayani lapisan yang lebih rendah. </p>

<p align = "justify">Dan terakhir, struktur mikrokernel dilakukan dengan Metode struktur menghilangkan komponen-komponen yang tidak diperlukan dari kernel dan mengimplementasikannya sebagai sistem dan program-program level user. Hal ini akan menghasilkan kernel yang kecil. Fungsi utama dari jenis ini adalah menyediakan fasilitas komunikasi antara program client dan bermacam pelayanan yang berjalan pada ruang user.</p>