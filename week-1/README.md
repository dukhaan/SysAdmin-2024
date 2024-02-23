    Nama            : Dukhaan Kamimpangan
    NRP             : 3122600003
    Kelas           : 2 D4 IT A
    Mata Kuliah     : Workshop Administrasi Jaringan
    Dosen Pengampu  : Dr. Ferry Astika Saputra S.T., M.Sc
    Pertemuan       : Minggu 1

# TUGAS 1

## 1. Installasi Debian

### Langkah-Langkah Installasi Debian Pada Virtual Box

1. Langkap pertama yang dilakukan untuk melakukan installasi adalah sebagai berikut :

   a. Virtual Box

   b. File ISO

   - Kunjungi situs resmi Debian di https://www.debian.org/CD/http-ftp/.
   - Pilihlah server Mirror Indonesia dan pilih versi “stable”.
   - Pilihlah versi yang sesuai dengan arsitektur sistem (misalnya, 64-bit)
   - Pilihlah file ISO Debian 11 atau versi diatasnya kemudian unduh

2. langkah kedua, buat mesin virtual baru di Virtual Box

   - Buka VirtualBox dan klik tombol “New” untuk membuat mesin virtual baru.

   <div align="center">
   <img src="./Img/1.png">
   <p><strong>Gambar 2.1:</strong>Machine</p>
   </div>

   - Beri nama pada mesin virtual (misalnya, “Debian-2024“) dan pilih jenis sistem operasi “Linux”.
   - Pilih versi “Debian (64-bit)” sebagai versi sistem operasi.
   - Centang pada "Skip Unattended Installation"
   - Klik button "Next"

   <div align="center">
   <img src="./Img/a.png">
   <p><strong>Gambar 2.2:</strong> New Machine</p>
   </div>

3. Langkah ketiga adalah melakukan konfigurasu hardware sebagai berikut :
   - Atur jumlah memori RAM dan CPU yang ingin dialokasikan untuk mesin virtual, kali ini gunakan spesifikasi sebagai berikut :
     1. RAM : 4096
     2. CPU : 2 Core
   - Klik button "Next"

<div align="center">
<img src="./Img/b.png">
<p><strong>Gambar 3.1:</strong> Konfigurasi Hardware</p>
</div>

4. Langkah Keempat melakukan konfigurasi Virtual Hard disk dengan partisi sebagai berikut :

   - Partisi HDD :
     1. / : 20 GB
     2. /storage : 5 GB
     3. swap : 1,5 GB

<div align="center">
<img src="./Img/b.png">
<p><strong>Gambar 4.1:</strong> Konfigurasi Virtual Hard disk</p>
</div>

5. Langkah Kelima adalah langkah terakhir sebelum proses installasi dimulai. Pada bagian Summary check kembali apakah spesifikasi yang dibutuhkan sudah sesuai. Apabila sudah klik button "Finish"

<div align="center">
<img src="./Img/b.png">
<p><strong>Gambar 5.1:</strong> Summary</p>
</div>

6. Langkah Keenam pilih mode BIOS yang ingin dijalankan untuk Intstallasi. Untuk Saat ini gunakan mode "Graphical install"

<div align="center">
<img src="./Img/Capture.JPG">
<p><strong>Gambar 6.1:</strong> Mode Bios</p>
</div>

7. Langkah Ketujuh pilih bahasa yang digunakan untuk installasi debian

<div align="center">
<img src="./Img/Capture1.JPG">
<p><strong>Gambar 7.1:</strong> Setting Bahasa</p>
</div>

8. Langkah Kedelapan pilih lokasi anda untuk mengatur zona waktu pada sistem

<div align="center">
<img src="./Img/Capture2.JPG">
<p><strong>Gambar 8.1:</strong> Pilih Other </p>
</div>

<div align="center">
<img src="./Img/Capture3.JPG">
<p><strong>Gambar 8.2:</strong> Pilih Asia </p>
</div>

<div align="center">
<img src="./Img/Capture4.JPG">
<p><strong>Gambar 8.3:</strong> Pilih Indonesia </p>
</div>

<div align="center">
<img src="./Img/Capture5.JPG">
<p><strong>Gambar 8.4:</strong> Pilih United States </p>
</div>

9. Langkah Kesembilan pilih tata letak keyboard

<div align="center">
<img src="./Img/Capture6.JPG">
<p><strong>Gambar 9.1:</strong> Pilih American English </p>
</div>
<div align="center">
<img src="./Img/Capture7.JPG">
<p><strong>Gambar 9.2:</strong> Proses instalasi components media</p>
</div>

10. Langkah Kesepuluh, input hostname dengan format "SysAdmin-NRP", Kemudian click continue. Untuk Domain neme tidak perlu di isi

<div align="center">
<img src="./Img/Capture8.JPG">
<p><strong>Gambar 10.1:</strong> Input hostname </p>
</div>

<div align="center">
<img src="./Img/Capture9.JPG">
<p><strong>Gambar 10.2:</strong> Domain name tidak perlu diisi</p>
</div>

11. Langkah Kesebelas, mengatur Root password

<div align="center">
<img src="./Img/Capture10.JPG">
<p><strong>Gambar 11.1:</strong> Atur root password </p>
</div>

12. Langkah Keduabelas, Inputkan nama user kemudian inputkan juga username anda

<div align="center">
<img src="./Img/Capture11.JPG">
<p><strong>Gambar 12.1:</strong> Input nama User </p>
</div>

<div align="center">
<img src="./Img/Capture12.JPG">
<p><strong>Gambar 12.2:</strong> Input username </p>
</div>

<div align="center">
<img src="./Img/Capture13.JPG">
<p><strong>Gambar 12.3:</strong> Mengatur password user account </p>
</div>

13. Langkah Ketigabelas, Pilih zona waktu sesuai dengan lokasi anda

<div align="center">
<img src="./Img/Capture14.JPG">
<p><strong>Gambar 13.1:</strong> Pilih zona waktu </p>
</div>

14. Langkah Keempatbelas, Mengatur partisi disk. Kali ini pilih Manual. Kemudian pilih Disk yang akan kamu settings partisinya dan klik "continue" dan "yes"

<div align="center">
<img src="./Img/Capture15.JPG">
<p><strong>Gambar 14.1:</strong> Pilih Manual </p>
</div>

<div align="center">
<img src="./Img/Capture16.JPG">
<p><strong>Gambar 14.2:</strong> Pilih Disk yang akan di settings partisinya </p>
</div>

<div align="center">
<img src="./Img/Capture17.JPG">
<p><strong>Gambar 14.2:</strong> Membuat partisi baru </p>
</div>

15. Langkah Kelimabelas, Memodifikasi partisi pada Hard Disk dengan ketentuan :

primary : 20 Gb -> ext4 -> /
primary : 5 Gb -> ext4 -> /storage
logical : 1.8 -> swap -> swap

<div align="center">
<img src="./Img/Capture33.JPG">
<p><strong>Gambar 15.1:</strong> Modifikasi Partisi </p>
</div>

<div align="center">
<img src="./Img/Capture34.JPG">
<p><strong>Gambar 15.2:</strong> Mengubah partisi dengan yang sudah dimodifikasi </p>
</div>

16. Langkah Keenambelas, Proses Installasi berjalan

<div align="center">
<img src="./Img/Capture35.JPG">
<p><strong>Gambar 16.1:</strong> Proses Installasi </p>
</div>

17. Langkah Ketujuhbelas, Pilih Archive mirror country kemudian pilih archive mirror country

<div align="center">
<img src="./Img/Capture37.JPG">
<p><strong>Gambar 17.1:</strong> Pilih Indonesia </p>
</div>

<div align="center">
<img src="./Img/Capture38.JPG">
<p><strong>Gambar 17.2:</strong> Pilih kartolo.sby.datautama.net.id </p>
</div>

18. Langkah Kedelepanbelas, Tidak perlu menginputkan HTTP proxy kemudian selanjutnya pilih system yang diperlukan.

<div align="center">
<img src="./Img/Capture39.JPG">
<p><strong>Gambar 18.1:</strong> HTTP Proxy dapat dikosongi </p>
</div>

<div align="center">
<img src="./Img/Capture41.JPG">
<p><strong>Gambar 18.2:</strong> Software yang mungkin dibutuhkan untuk diinstall  </p>
</div>

19. Langkah Kesembilanbelas, Untuk memulai Grub bootloader pada hard disk utama pilih "Yes". Selanjutnya pilih tempat grub loader akan diinstal. Terakhir, Proses installasi telah selesai.

<div align="center">
<img src="./Img/Capture42.png">
<p><strong>Gambar 19.1:</strong> Install GRUB boot loader </p>
</div>

<div align="center">
<img src="./Img/Capture43.png">
<p><strong>Gambar 19.2:</strong> Pilih device yang digunakan untuk GRUB </p>
</div>

<div align="center">
<img src="./Img/Captureend.JPG">
<p><strong>Gambar 19.3:</strong> Proses installasi telah selesai klik finish </p>
</div>

**DEBIAN BERHASIL DIINSTALL PADA VIRTUAL BOX**

<div align="center">
<img src="./Img/Capture44.png">
<p> Install GRUB boot loader </p>
</div>

## 2. Perbedaan Debian 12 (Bookworm) dan Debian 11 (Bullseye)

| Perbedaan         | Debian 12 (Bookworm)                                                          | Debian 11 (Bullseye)                                                              |
| ----------------- | ----------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Versi Kernel      | 6.1                                                                           | 5.10                                                                              |
| Kebutuhan Sistem  | Mungkin lebih tinggi                                                          | Moderat                                                                           |
| Penerapan systemd | Aktivasi jurnal persisten oleh default dengan fallback ke penyimpanan volatil | Tidak dijelaskan, tetapi mungkin ada perbedaan versi                              |
| Perbedaan Package | Lebih baru, 11.089 paket baru, non-free software disertakan dalam ISO primer  | Tidak dijelaskan jumlahnya, namun non-free packages disertakan dalam ISO terpisah |

## 3. Fungsi dari File "/etc/group" dan Formatnya

File "/etc/group" berisi informasi tentang grup-grup pengguna pada sistem. Setiap baris mewakili satu grup dan memiliki format sebagai berikut:

nama_grup:password:ID_grup:anggota1,anggota2,...

- _nama_grup_: Nama grup.
- _password_: Biasanya berisi "x", dan sebenarnya password grup disimpan di "/etc/gshadow".
- _ID_grup_: ID numerik unik untuk grup.
- _anggota1,anggota2,..._: Daftar pengguna yang termasuk dalam grup tersebut.

## 4) Perbedaan antara "su" dan "su -"

- _su_: Mengganti pengguna tanpa mengganti lingkungan shell. Variabel lingkungan, seperti PATH, tetap dari pengguna sebelumnya.
- _su -_: Mengganti pengguna dan juga mengganti ke lingkungan shell yang baru. Ini sama dengan login sebagai pengguna tersebut dan membawa seluruh lingkungan pengguna tersebut.

## 5) Fungsi dari "sudo"

"sudo" (superuser do) adalah perintah yang memungkinkan pengguna untuk menjalankan perintah sebagai pengguna lain, biasanya sebagai superuser (root). Ini memberikan hak akses terbatas dan terkontrol kepada pengguna, yang dicatat dan dilacak.

## 6) Langkah-langkah penambahan user sebagai user sudo

1. Gunakan perintah su - untuk masuk sebagai root.
2. Setelah masuk sebagai root, jalankan perintah visudo untuk mengedit file konfigurasi sudoers.
3. Tambahkan baris berikut di bawah baris yang mencakup user root pada bagian " # User privilege specification":

   username ALL=(ALL:ALL) ALL

   (Gantilah "username" dengan nama pengguna yang ingin User tambahkan.)

4. Simpan dan keluar dari editor.

Dengan langkah-langkah ini, pengguna yang User tambahkan akan memiliki hak akses sudo di sistem. Pastikan untuk memberikan hak akses sudo hanya kepada pengguna yang membutuhkannya dan amankan konfigurasi sudoers dengan hati-hati.

##
