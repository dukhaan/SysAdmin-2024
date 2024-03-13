---
marp: true
---

<!-- headingDivider: 3-->

<!-- _color_: yellow-->

# Dasar Sistem Administrasi Jaringan

Dr. Ferry Astika Saputra S.T., M.Sc

# Oleh Kelompok 4

1. Dukhaan Kamimpangan / 3122600003
2. Rakha Putra Pratama / 3122600005
3. Diah Aulia Kusuma Putri / 3122600008

# 8.1.1 Software Sources

8.1.1 The sources.list file
File sources.list adalah konfigurasi utama yang menentukan sumber perangkat lunak yang dapat diakses oleh sistem. Di dalamnya, kita mendefinisikan repositori-respositori yang akan digunakan untuk mengunduh dan menginstal perangkat lunak.

Untuk dapat mengedit sources.list, command yang digunakan adalah

1. apt edit-sources
2. nano /etc/apt/source. list

# 8.1.2 About Repositories, Branches, and Sections/Components

Debian mengorganisir paket-paket perangkat lunaknya di dalam repositori. Repositori ini dibagi menjadi cabang dan bagian/komponen. Ada 4 bagian dalam repositori resmi Debian:

1. main: Mematuhi DFSG tanpa ada ketergantungan "non-free"
2. non-free-firmware: Firmware non-bebas yang disertakan secara default sejak Debian 12
3. ontrib: Mematuhi DFSG dengan beberapa ketergantungan "non-free"
4. non-free: Tidak mematuhi DFSG

Hanya paket-paket dalam bagian/komponen main yang didukung secara resmi oleh proyek Debian dan merupakan perangkat lunak 100% bebas. Sementara itu, yang disarankan dalam contrib, non-free, dan non-free-firmware adalah sebagian atau sepenuhnya non-bebas.

## 8.1.3 Backport Packages (8.1.3)

Debian juga menawarkan repositori khusus yang disebut backports, yang berisi versi lebih baru dari beberapa aplikasi. Repositori ini tidak diaktifkan secara default, tetapi tidak menimbulkan risiko khusus bagi sistem Anda: repositori "reguler" memiliki prioritas tertinggi selama proses pembaruan.

## 8.1.4 Modifying the Repositories

Sebelum Anda mulai memodifikasi sumber perangkat lunak sistem Anda, Anda harus sadar akan risiko yang Anda ambil dengan menggunakan komponen "contrib" atau "non-free" dari cabang arsip:

1. Kurangnya kebebasan untuk jenis paket ini
2. urangnya dukungan oleh proyek Debian (Anda tidak dapat memelihara sebuah perangkat lunak tanpa memiliki kode sumbernya)
3. Pencemaran pada sistem Debian Anda yang sepenuhnya bebas.

# 8.2 APT in a Terminal

Bagian ini menyajikan perintah dasar untuk mengelola paket Debian dengan APT (Advanced Package Tool) melalui terminal. Meskipun Debian juga mendukung "aptitude" sebagai manajer paket alternatif, namun karena manual ini ditujukan untuk pemula, kita akan fokus pada penggunaan APT saja. Untuk informasi lebih lanjut tentang aptitude, dapat ditemukan di wiki Debian yang khusus untuk itu: https://wiki.debian.org/Aptitude.

# 8.2 Perintah 'User' untuk Mencari dan Menampilkan Informasi

Perintah-perintah ini dapat dieksekusi oleh pengguna biasa, karena tidak berdampak pada sistem.

1. Command -> Description
2. apt show foo -> Display information about the package foo
3. apt search foo -> Lookfor packages corresponding to the foo
4. apt-cache policy foo -> Display the available version of foo

# 8.2.1 'Administrator' Mode Commands for System Maintenance

Perintah-perintah ini harus dieksekusi dengan hak administrator "root", karena berdampak pada sistem. Untuk masuk ke mode administrator dari terminal, ketik "su -": kemudian Anda akan diminta kata sandi administrator.

1. Command -> Description
2. apt update -> Update the repositories metadata
3. apt install foo -> Install the foo package and its dependesncies
4. apt upgrade -> Secured update of the installed package

---

5. Command -> Description
6. apt full-upgrade -> Upgrade of installed packet, by adding/removing other packages if necessary
7. apt remove foo -> Remove the foo package, but not the configuratrion files
8. apt autoremove -> Auto remove the unecessary packages
9. apt purge foo -> Purge the foo package and its configuration files
10. apt clean -> Clean the local cache of the installed package
11. apt auto clean -> Clean the local cache of the obsolete packages
12. apt-mark-showmanual -> Mark a package as being “manually-installed”

# 8.3 Software: The Simplified Package Manager

Perangkat lunak ini memudahkan pengguna untuk mengelola aplikasi Debian. Pengguna dapat mencari, menginstal, menghapus, atau memperbarui paket yang berisi aplikasi dengan mudah. Perangkat lunak ini biasanya dapat ditemukan di kategori "Sistem" dalam menu, atau langsung dapat diakses dari kotak pencarian Gnome dengan mengetik "Perangkat Lunak".

# 8.3.1 Software: Searching an Application

Cara pertama adalah dengan langsung mengklik tombol pencarian (simbol kaca pembesar), atau dengan memilih salah satu kategori yang ditampilkan.

# 8.3.2 Software: Software: Installing an Application

Anda bisa menginstal aplikasi dengan mudah dengan mengklik area deskripsi aplikasi dan kemudian tombol “Instal”. Kata sandi administrator akan diminta. Anda bisa mengikuti proses instalasi di jendela utama dan kemudian langsung menjalankan aplikasi yang baru diunduh.

# 8.3.3 Software: Removing an Application

Anda dapat menghapus aplikasi dengan mengunjungi kategori “Terinstal” (di bagian atas antarmuka) dan kemudian mengklik tombol “Hapus”. Anda akan diminta untuk konfirmasi:

1. Memilih aplikasi untuk penghapusan.
2. Konfirmasi.

# 8.3.4 Software: upgrading your applications

Anda dapat memperbarui sistem Anda dari bagian “Pembaruan” yang akan menunjukkan pembaruan yang tersedia dan/atau sudah diunduh. Jika tidak ada pembaruan yang tersedia, Anda dapat memeriksa repositori dengan menggunakan tombol khusus di bagian kiri atas.
_Catatan bahwa untuk pembaruan yang lebih ringan, restart tidak diperlukan. Setelah reboot, jendela pesan di desktop memberi tahu Anda bahwa instalasi berhasil._

# 8.3.5 Software: modify packages repositories

Aplikasi “Perangkat Lunak” cukup sederhana, tetapi masih memungkinkan Anda untuk mengkonfigurasi repositori secara grafis. Dari menu, pilih “Repositori”. Anda dapat menambahkan sumber “non-free” dan/atau menentukan frekuensi pembaruan repositori. Informasi alamat repositori yang ditampilkan berasal dari file sources.list Anda

1. Menu repositori.
2. Modifikasi repositori.

Setelah repositori Anda dimodifikasi, Anda harus me-reload paket informasi. Sebuah pesan akan muncul:

1. Memperbarui informasi paket.
2. Me-refresh cache.

# 8.3.6 Automatic updates with Software

Untuk memanfaatkan sistem Anda tanpa harus khawatir tentang pembaruan, Anda dapat mengaktifkan mekanisme pembaruan otomatis. Dari menu “Perangkat Lunak”, pilih “Preferensi Pembaruan”.

# 8.4 Discover: The KDE Package Manager

Gnome menggunakan "Software" untuk mengelola aplikasi secara sederhana, sedangkan KDE mengintegrasikan Discover, sebuah program yang intuitif dan efisien.
Discover memungkinkan Anda untuk mencari, menginstal, menghapus, atau memperbarui aplikasi Anda dari antarmuka tunggal. Anda juga dapat mengubah sumber perangkat lunak Anda untuk menginstal - atau tidak - beberapa aplikasi non-gratis.
Discover diluncurkan dengan mudah dari menu utama KDE > Aplikasi> Sistem > Pusat Perangkat Lunak.

# 8.4.1 Search and install with Discover

Untuk menemukan sebuah aplikasi, ketikkan namanya di bidang pencarian yang ditentukan atau kunjungi berbagai kategori Discover. Kemudian klik tombol "Instal" sudah cukup:

1. Mencari aplikasi dengan Discover
2. Menelusuri kategori dengan Discover

Anda akan diminta untuk mengonfirmasi setiap tindakan pada perangkat lunak bersama dengan kata sandi administrator. Proses tersebut kemudian akan diluncurkan di latar belakang. Anda dapat mengikuti kemajuan modifikasi dalam area notifikasi KDE.

# 8.4.1 Install Plasma desktop widgets and addons

Discover memungkinkan Anda untuk menambahkan komponen tambahan ke lingkungan Plasma Anda. Untuk melakukannya, kunjungi > Add-ons Plasma > Addon desktop Plasma

Beberapa modul tambahan juga tersedia untuk aplikasi Anda > Addon aplikasi

# 8.4.2 Uninstalling an application with Discover

Dengan Discover, cukup kunjungi kategori "Terinstal" kemudian klik "Hapus" > Menghapus dengan Discover.

# 8.4.3 Discover: updating your applications

Ketika KDE memberi tahu Anda tentang satu atau lebih pembaruan, itu adalah "Discover" yang melakukannya. Untuk memeriksa pembaruan secara "manual", klik tombol khusus:

1. Memeriksa pembaruan > Cukup klik "Perbarui semua" dan konfirmasi dengan kata sandi administrator.
2. Memulai pembaruan
3. Kata sandi diminta untuk pembaruan
4. Kemajuan pembaruan

Demikian juga dengan manajemen perangkat lunak, Anda dapat mengikuti prosesnya dalam area notifikasi KDE. Dan sebuah pesan akan memberi tahu Anda pada akhir proses.

# 8.4.4 Discover: managing repositories

Pustaka perangkat lunak KDE memungkinkan Anda untuk mengubah sumber aplikasi Anda tanpa menggunakan terminal. Pergi ke bagian "Pengaturan" Discover, entri-entri tersebut menampilkan alamat repositori dari file sources.list Anda > mengelola repositori

# 8.5 Synaptic: the comprehensive package manager

Synaptic adalah antarmuka grafis komprehensif dari manajer paket Debian. Ini memungkinkan visi total terhadap paket yang diusulkan, baik yang terinstal maupun tidak. Ini jauh lebih rinci daripada Pusat Perangkat Lunak atau Discover karena menampilkan kumpulan paket yang tersedia secara penuh (termasuk pustaka).

- Ini menyediakan fungsionalitas yang sama seperti apt.
- Anda perlu memasukkan kata sandi administrator untuk membuka dan menggunakan Synaptic.
- Koneksi internet aktif juga diperlukan untuk menginstal atau memperbarui perangkat lunak Anda.

# 8.5.1 Synaptic: Main interface

Jendela Synaptic terbagi menjadi 4 area: bilah alat di bagian atas, panel kiri yang memungkinkan berbagai cara pengurutan dan pemilihan paket, panel tengah yang menampilkan daftar paket itu sendiri, dan di bawahnya, panel yang menyimpan deskripsi paket yang saat ini dipilih (pemilihan dilakukan dengan mengklik).

Di depan setiap paket, Anda melihat kotak kecil (putih untuk paket yang tidak terinstal, hijau ketika terinstal, merah ketika rusak). Sebelah kotak status ini, logo

Debian menunjukkan bahwa paket ini "bebas" (seperti kebebasan).
Jangan ragu untuk mengklik semua menu yang berbeda untuk menjelajahi Synaptic dan menjadi lebih familiar dengannya. Ini adalah cara yang baik untuk menemukan berbagai fungsinya.

---

Jangan takut merusak sistem Anda karena tidak akan ada yang benar-benar terjadi sampai Anda mengklik tombol "Terapkan". Di atas itu, pesan yang meminta konfirmasi akan selalu ditampilkan terlebih dahulu.

Hal pertama yang harus dilakukan ketika Anda meluncurkan Synaptic adalah mengklik tombol "Muat Ulang" untuk memperbarui semua informasi (metadata) tentang repositori, paket, dan aplikasi yang tersedia.

# 8.5.2 Managing the repositories with Synaptic

Repositori memungkinkan untuk memperbarui dan menginstal paket tambahan.
Repositori telah dikonfigurasi selama proses instalasi tetapi Anda dapat mengelolanya kapan saja, jika diperlukan. Buka manajer paket Synaptic (menu Sistem > Manajer paket Synaptic). Di bilah menu atas, klik "Pengaturan, dan kemudian" Repositori”.

Anda akan melihat bahwa daftar tersebut sesuai dengan konten dari file sources.list /etc/apt/sources.list yang disebutkan dalam bab 8.1.1.
Sekarang, Anda dapat mengubah sumber repositori Anda sesuai keinginan Anda. Cukup klik pada sumber untuk memodifikasinya, atau pada tombol “Baru” untuk menambahkan sumber lain.

---

Setelah modifikasi Anda divalidasi, aplikasi akan mengundang Anda untuk memuat ulang daftar repositori untuk memperhitungkan perubahan Anda.

Perhatikan bahwa jika Anda ingin menggunakan antarmuka yang disederhanakan "hanya-kotak-centang" pada salah satu desktop Xfce, LXDE, atau LXQt, Anda perlu menginstal paket "software-properties-gtk".

# 8.5.3 Updating the system with Synaptic

Sebelum memperbarui sistem, perlu "Muat Ulang" daftar paket, dengan mengklik tombol yang sesuai, atau dengan pergi ke menu "Edit > Muat Ulang Informasi Paket" (atau bahkan [Ctrl]+r jika Anda ingin menggunakan pintasan keyboard). Tindakan ini memeriksa apakah versi paket yang berada di sistem Anda adalah yang paling baru atau tidak.

Kemudian klik “Tandai Semua Pembaruan” atau pergi ke menu “Edit > Tandai Semua Pembaruan…”.
Jika tidak ada yang terjadi setelah Anda mengklik “Perbarui semua”, itu berarti bahwa sistem Anda sudah terbaru. Anda dapat menutup Synaptic.
Jika ada beberapa paket untuk diinstal atau diperbarui, mereka akan dijelaskan. Anda dapat melihatnya dengan memilih bagian "Status" > "terinstal (bisa diperbarui)":

---

Muncul jendela baru dengan daftar paket yang akan diperbarui serta dependensi tambahan, jika diperlukan:

Anda hanya perlu mengklik tombol “Tambahkan ke seleksi” kemudian tombol “Terapkan”, dan terima konfirmasi yang diminta:

Proses pembaruan sistem dimulai dengan mengunduh paket-paket, dan dilanjutkan dengan instalasi mereka.

Sebuah pesan menginformasikan Anda bahwa semua perubahan telah diterapkan.

# 8.5.4 Searching for a software

Jika Anda mengetahui nama paket atau mencari sesuatu dengan tepat, klik tombol pencarian (di bilah atas) dan masukkan kata kunci pencarian Anda di jendela yang terbuka > mencari aplikasi

Jika Anda tidak tahu nama paket yang Anda butuhkan, Anda dapat memfilter daftar menggunakan filter berdasarkan bagian, status, asal, dll ...

Misalnya, jika Anda mencari game, klik pada Bagian di bagian bawah panel kiri, gulir ke bawah ke bagian "Game dan Hiburan", klik di atasnya, dan semua paket yang berkaitan dengan game dan hiburan akan muncul di panel tengah.

# 8.5.5 Installing a package with Synaptic

Untuk menginstal satu atau beberapa paket, klik kanan pada kotak kecil di depan nama paket, dan pilih opsi "Tandai untuk Instalasi" > menandai paket untuk instalasi

Jika, untuk menjadi fungsional, paket ini memerlukan instalasi paket lain (dependensi terkenal), mereka secara otomatis ditambahkan ke dalam seleksi > dependensi ditambahkan

Kemudian, Anda hanya perlu mengklik tombol "Terapkan", dan konfirmasi ringkasan perubahan yang akan diterapkan.

1. Menerapkan perubahan
2. Ringkasan perubahan yang menunggu

Paket-paket diunduh dan diinstal. Anda dapat mengikuti seluruh proses di dalam antarmuka synaptic:

1. Mengunduh paket yang akan diinstal
2. Operasi berhasil

# 8.5.5.1 Reinstall a package

Terkadang kita ingin menginstal ulang paket yang sudah terinstal. Dalam hal ini, pilih opsi "Tandai untuk Instalasi Ulang". Ini memungkinkan, misalnya, untuk mengembalikan konfigurasi default untuk aplikasi jika Anda telah memodifikasinya.

# 8.5.6 Uninstall a package with Synaptic

Seperti saat instalasi, klik kanan pada kotak kecil di depan nama paket, dan pilih opsi "Tandai untuk Dihapus". Kemudian klik "Terapkan".
Penghapusan sederhana membuat file konfigurasi paket tetap ada di sistem Anda, jika Anda ingin menginstalnya kembali nanti.
Untuk menghapus juga file konfigurasi, pilih opsi "Tandai untuk Penghapusan Lengkap" (setara dengan "purge" dalam baris perintah terminal) > memilih paket untuk dihapus

# 8.5.6.1 Synaptic: cleaning useless packages

Seringkali, ketika perangkat lunak dihapus, beberapa paket (dependensi) tetap ada di sistem meskipun tidak lagi berguna, karena semua paket yang membutuhkannya sudah hilang. Paket-paket yang tidak berguna ini dapat dengan mudah dihapus dengan Synaptic.

Ketika Synaptic diluncurkan, klik tombol "Status" di bagian bawah panel kiri. Jika kategori "Terinstal (Dapat dihapus otomatis)" muncul, klik di atasnya untuk menampilkan paket-paket yang sesuai (lihat gambar di bawah) > paket yang dapat dihapus otomatis.

Yang perlu Anda lakukan selanjutnya adalah mengklik kanan pada setiap paket di panel tengah, dan pilih opsi "Tandai untuk Penghapusan Lengkap". Setelah semua paket ditandai, klik tombol "Terapkan".

# 8.5.6.2 Removing configuration residues

Meskipun seseorang memilih untuk sepenuhnya menghapus perangkat lunak, beberapa sisa konfigurasi mungkin masih tetap ada di sistem, tetapi mereka juga dapat dengan mudah dihapus dengan Synaptic.
Klik tombol “Status” di bagian bawah panel kiri. Jika kategori “Tidak Terinstal (konfigurasi sisa)” muncul, pilihlah.
Yang harus Anda lakukan selanjutnya adalah mengklik kanan pada setiap paket di panel tengah, dan pilih opsi “Tandai untuk Penghapusan Lengkap”. Setelah semua paket ditandai, klik tombol “Terapkan”.

# 8.5.7 Look at detailed information on a package

Dengan mengklik pada sebuah paket, deskripsi paket tersebut akan ditampilkan di bagian bawah panel tengah Synaptic. Untuk mendapatkan informasi lebih lanjut tentang sebuah paket, klik kanan padanya, dan pilih Properti, atau pergi ke menu “Paket > Properti”.

Maka Anda akan mengetahui segalanya - benar-benar segalanya - tentang paket ini: dependensi, file yang terinstal, ukuran, dan versi.

# 8.5.8 Synaptic preferences

"Preferensi" adalah kategori yang memiliki nama yang jelas, ada di sebagian besar aplikasi, dan juga hadir di sini ... Tetapi ingatlah bahwa Synaptic adalah kasus yang sangat spesial: ia mengelola seluruh set perangkat lunak yang diinstal di sistem Anda. Ketika Anda menghapus sebuah program, itu tidak masuk ke tempat sampah (di mana Anda bisa mengambilnya kembali)!
Setelah peringatan mengerikan ini, mari kita beralih ke pengaturan yang tersedia untuk Synaptic. Jendela Preferensi (diluncurkan melalui menu Pengaturan > Preferensi) menampilkan 6 tab yang berbeda > Jendela Preferensi

---

- Umum: opsi di sana cukup eksplisit. Catatan: Anda dapat membatalkan pilihan “Anggap paket yang direkomendasikan sebagai dependensi”, jika itu membantu Anda menjaga sistem yang sangat ringan. Tetapi ini bisa menimbulkan masalah saat menginstal paket baru di masa depan. Oleh karena itu, opsi ini perlu ditangani dengan hati-hati.
- Kolom dan Fon: memungkinkan Anda untuk menampilkan/menyembunyikan beberapa kolom dalam daftar paket, dan menentukan font, jika diperlukan.
- Warna: Anda dapat menentukan di sini warna paket sesuai dengan statusnya.

---

- Berkas: Ketika Anda menginstal sebuah perangkat lunak, itu pertama-tama disimpan di cache (yang merupakan folder khusus dari sistem file) sebelum dikompresi dan diinstal. Paket-paket ini dapat menghabiskan lebih banyak ruang disk seiring penggunaan komputer Anda. Di sini Anda dapat menghapusnya secara langsung atau mengkonfigurasi tindakan otomatis.
- Jaringan: Ini adalah cara Synaptic terhubung ke Internet. Anda harus tahu apakah situasi Anda memerlukan modifikasi dari parameter-parameter ini.
- Distribusi: Menentukan perilaku peningkatan paket dan sangat eksplisit. Jika ragu, jangan mengubahnya!

# 8.6 Cleaning the system

Meskipun kapasitas hard disk meningkat secara dramatis selama beberapa tahun terakhir, Anda mungkin memerlukan beberapa ruang kosong. Beberapa skrip mengotomatisasi proses pembersihan disk, namun saya lebih suka memeriksanya sebelum menggunakan perintah rm.

# 8.6.1 Disk space information

Hal pertama yang harus dilakukan, tentu saja, adalah mengetahui ruang yang digunakan di disk Anda. Beberapa alat tersedia untuk Anda, mulai dari terminal Anda:

Ruang disk dalam mode terminal -
Ringkasan penggunaan ruang disk untuk setiap titik mount sistem (disk dan partisi) dengan perintah df:
\_df -h
Fitesystem 3ize Used Avait Use% MountPoint
udev 983M © 983M ©% /dev
tmpfs 2©©M 8,1M 192M 5% /fun
/dev/sda1 48G 16G 3©G 35% /
tmpfs 998M © 998M ©% /dev/shm
tmpfs 5,©M 4,©K 5,©M 1% /fun/tock

---

**List your repertories sorted by decreasing size**
Menampilkan direktori Anda yang berat menggunakan du dan sort (unitnya adalah megabyte):
_usef$debian-pc:b$ du -ms \* | soft -nf_
_585 Music_
_281 Videos_
_232 Documents_
_42 Pictufes_
_26 Dowtoads_

---

**- Ncdu -**
Sebuah analisis ruang disk dalam mode konsol. Untuk menjalankannya, cukup ketik “ncdu” di terminal Anda. Untuk menginstal perangkat lunak ini (dalam mode administrator):
_apt update && apt instatt ncdu_

**- Baobab -**
Sebuah analisis ruang disk dalam mode grafis, terintegrasi dalam Gnome tetapi tersedia dalam lingkungan lain dengan:

_apt update && apt instatt baobab_

# 8.6.2 Cleaning the packages

Apt/aptitude/dpkg adalah manajer paket Debian yang biasa digunakan. Saat Anda menginstal sebuah paket, arsip-nya/source/deb disimpan di sistem Anda (di folder /var/cache/apt/archives/) untuk memungkinkan penginstalan kembali tanpa koneksi Internet. Untuk membersihkan "cache apt" gunakan perintah sederhana dalam mode administrator.

# 8.6.3 Emptying the trash bins

Tiga tempat sampah yang berbeda harus diperhitungkan:
Tempat sampah pengguna: ~/.local/share/Trash/. Anda dapat mengosongkannya dengan manajer file sistem (bab.3.6.2.5), atau dengan terminal:
_fm -Rf b/.tocat/shafe/Tfash/\*_

Tempat sampah administrator: /root/.local/share/Trash/. Untuk mengosongkannya dengan cara yang benar, gunakan terminal dalam mode administrator :
_fm -Rf /foot/.tocat/shafe/Tfash/\*_

Tempat sampah eksternal: berlokasi pada disk eksternal Anda, biasanya dinamai ‘/media/y- our_id/your_disk/.Trash_1000’, di mana your_id sesuai dengan nama login Anda.

# 8.6.4 Purging application caches

Beberapa aplikasi menggunakan folder “cache”, di mana mereka menyimpan gambar, video, dan informasi lainnya agar berjalan lebih cepat. Biasanya data ini tidak memakan terlalu banyak ruang disk, namun jika (menggunakan alat-alat yang dijelaskan di atas) Anda mendeteksi bahwa sebuah folder menjadi terlalu besar, jangan ragu untuk menghapusnya.

# 8.6.5 Purging the thumbnails

Setiap kali Anda membuka folder yang berisi gambar atau video, thumbnail dibuat untuk mewakili file grafis tersebut. Thumbnail ini disimpan dalam folder tertentu untuk digunakan kembali, daripada harus menghitung ulang setiap kali Anda mengakses jenis file ini.
Permasalahannya timbul ketika Anda menghapus sebuah file grafis, karena thumbnail-nya tetap ada di sistem, dan ini menyebabkan sejumlah ruang disk terbuang untuk menyimpan thumbnail yang tidak terpakai.
Untuk menghapusnya, cukup hapus folder yang sesuai.

**Folder ini akan dibuat kembali, ketika sistem perlu menyimpan thumbnail yang baru dibuat.**

# 8.7 Installing external “.deb” packages

Debian GNU/Linux menggunakan sistem repositori paket untuk mengelola perangkat lunak dan meningkatkan keamanan sistem Anda. Namun, terkadang Anda mungkin memerlukan paket eksternal dalam format ".deb".

deb adalah singkatan dari "debian", perusahaan induknya. Untuk mendistribusikan perangkat lunaknya, Debian menggunakan format arsip khusus: ".deb". Ini adalah format terkompresi, seperti ".zip" yang Anda gunakan untuk menyimpan data Anda. Arsip ".deb" ini dikenali oleh manajer paket Debian yang berbeda (APT dan antarmuka grafisnya Synaptic) dan dengan demikian dapat diolah lebih mudah.

# 8.7.1 Installation in graphic mode with GDebi

GDebi adalah utilitas grafis yang memungkinkan instalasi paket eksternal dalam format ".deb", sambil mengelola dependensi.
Untuk menginstalnya, cari "gdebi" dalam manajer paket favorit Anda (Synaptic, Discover, Software) atau lebih sederhana lagi dari terminal dalam mode administrator menggunakan "su".
_apt update && apt instatt gdebi_

# 8.7.2 Installation in terminal mode with Dpkg

Dpkg adalah utilitas perangkat lunak yang menangani paket-paket, seperti halnya apt, tetapi tanpa mengelola dependensi. Ini berarti bahwa jika Anda menggunakan dpkg untuk menginstal paket eksternal, Anda perlu menginstal paket-paket "dependen" satu per satu dari terminal Anda. Dpkg terintegrasi secara default di Debian, dan harus digunakan dalam mode administratif.
Untuk menginstal paket eksternal:

Anda akan mendapatkan pesan kesalahan jika beberapa dependensi hilang. Kemudian cukup instalasi dengan cara klasik menggunakan apt:

Kemudian mulai ulang instalasi paket eksternal Anda.

# 8.8 Installing Flatpak applications

Flatpak adalah sistem aplikasi virtualisasi untuk distribusi GNU/Linux. Tujuannya adalah untuk menyediakan lingkungan "sandbox" yang aman, terisolasi dari sistem lain, di mana pengguna dapat menjalankan aplikasi yang tidak divalidasi oleh repositori distribusi (versi uji coba, misalnya).

# 8.8.1 Installing Flatpak

Untuk menggunakan aplikasi dalam format Flatpak, Anda harus menginstal paket yang sesuai terlebih dahulu. Dari terminal Anda dalam mode administrator:
_apt update && apt install flatpak_

Anda sekarang dapat mengunduh dan menginstal paket-paket flatpak dengan mengunjungi salah satu situs web yang mengelompokkan aplikasi-aplikasi ini seperti Flathub.

# 8.8.2 Add a Flatpak repository

Untuk menambahkan repositori seperti Flathub, ketik di terminal Anda:
_flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo_

Anda akan diminta kata sandi administrator. Dan Anda harus me-restart sistem Anda untuk memperhitungkan perubahan.

# 8.8.3 Manage Flatpak applications under Gnome with Software

Untuk mengelola flatpak dalam manajer perangkat lunak Anda, Anda harus menambahkan plugin yang sesuai dengan lingkungan Anda. Untuk GNOME, dalam terminal dan dalam mode administrator:
_apt update && apt install gnome-software-plugin-flatpak_

Sekarang Anda dapat mengelola flatpak Anda seperti aplikasi lainnya.

# 8.8.4 Manage Flatpak applications under KDE with Discover

Untuk menggunakan Discover, di bawah Kde, Anda harus menginstal plugin yang sesuai. Di terminal dan dalam mode administrator:
_apt update && apt install plasma-discover-flatpak-backend_

Anda sekarang dapat mengelola flatpak Anda seperti aplikasi lainnya.

# 8.8.5 Manage Flatpak applications from your terminal

Perintah Dasar untuk Mengelola Flatpak dari Terminal

- **flatpak search flatpak_name**: Mencari flatpak di semua repositori.
- **flatpak install repository flatpak_name**: Menginstal flatpak dari repositori.
- **flatpak uninstall flatpak_name**: Menghapus flatpak.
- **flatpak uninstall --unused**: Menghapus dependensi yang tidak terpakai.
- **flatpak update**: Memperbarui semua flatpak yang terinstal.
- **flatpak run flatpak_name**: Meluncurkan flatpak.

# 8.8.6 Remove a Flatpak application

Jika Anda telah menginstal flatpak secara grafis dari Software atau Discover, cukup hapus dari menu aplikasi terinstal dari manajer perangkat lunak Anda.

# 8.8.7 Some Flatpak repositories

Beberapa repositori yang menggunakan format Flatpak dan perintah yang harus dieksekusi untuk menambahkan repositori mereka.

# 8.9 Who is this Sid guy?

Pertama-tama, perlu diketahui bahwa beberapa cabang distribusi Debian ada secara bersamaan. Ada oldstable, stable, testing, dan unstable, serta cabang eksperimental.

Distribusi Stable adalah distribusi resmi Debian, yang dirilis saat ini dan dikelola serta diperbarui oleh tim Debian. Perubahan yang dilakukan hanya terkait dengan pembaruan keamanan dan perbaikan bug. Disarankan untuk memilih versi ini.

Distribusi Oldstable adalah versi stabil sebelumnya. Biasanya didukung oleh tim Debian selama satu tahun setelah rilis versi stable baru. Namun, bisa bertahan lebih lama jika cukup banyak individu atau perusahaan yang melanjutkan pemeliharaannya. Kemudian disebut distribusi LTS (Long Term Support): umur pakainya diperpanjang.

---

Distribusi Testing adalah versi Stabil di masa depan. Digunakan untuk mempersiapkan versi stabil berikutnya. Ketika semuanya baik-baik saja, fitur yang ditargetkan oleh tim Debian sudah termasuk, dan setelah periode pembekuan perangkat lunak dan perburuan bug, versi Testing menjadi distribusi Stabil resmi yang baru.

Distribusi Unstable, atau dikenal sebagai Sid, adalah versi yang menerima semua versi paket baru dan berada di ujung inovasi, tetapi tidak terlalu stabil: itu adalah laboratorium penelitian. Meskipun demikian, beberapa petualang yang berani menggunakannya setiap hari.

---

Distribusi Eksperimental bukanlah distribusi Debian sebenarnya, tetapi lebih merupakan repositori tempat versi perangkat lunak alpha atau beta diuji.

Semua distribusi ini diberi julukan yang diambil dari karakter dalam kartun Toy Story. Saat ini, nama versi stable adalah Bookworm, nama versi testing adalah Trixie, nama versi oldstable adalah Bullseye, dan Experimental tidak memiliki julukan.
