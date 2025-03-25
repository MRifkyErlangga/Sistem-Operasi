**M.Rifky Erlangga_TK@B# Sistem-Operasi**
1. Eksekusi Seluruh Profile yang Ada
**a. Edit /etc/profile dan Tambahkan Pesan**
Jalankan perintah berikut sebagai root:
echo 'echo "Profile dari /etc/profile"' | sudo tee -a /etc/profile
Verifikasi perubahan:
cat /etc/profile | grep "Profile dari /etc/profile"

**b. Edit Semua File Profile Pengguna**
Gantilah username dengan nama pengguna yang sesuai:
username="stD02001"
echo 'echo "Profile dari ~/.bash_profile"' >> /home/$username/.bash_profile
echo 'echo "Profile dari ~/.bash_login"' >> /home/$username/.bash_login
echo 'echo "Profile dari ~/.profile"' >> /home/$username/.profile
echo 'echo "Profile dari ~/.bashrc"' >> /home/$username/.bashrc

**c. Jalankan su dan su -**
su mahasiswa
exit

su - mahasiswa
exit

Perbedaan:
su mahasiswa → Hanya mengganti user tanpa mengubah lingkungan (environment).
su - mahasiswa → Mengubah user dan menerapkan environment shell sepenuhnya.

2. Prompt String (PS1)
**a. Edit .bash_profile dan Ubah PS1**
Tambahkan perintah berikut di .bash_profile:
echo 'export PS1="> "' >> ~/.bash_profile
source ~/.bash_profile
Sekarang, prompt akan berubah menjadi:

**b. Eksperimen dengan PS1**
Coba format PS1 lainnya:
PS1="\u > "   # Menampilkan username
PS1="\h:\w > " # Menampilkan hostname dan direktori kerja
export PS1

3. Logout dengan Pesan
Edit .bash_logout dan tambahkan perintah berikut:
echo 'echo "Terima kasih atas sesi yang diberikan"' >> ~/.bash_logout
Setiap kali logout, pesan berikut akan muncul:
Terima kasih atas sesi yang diberikan

4. Membuat dan Menjalankan Skrip Background
**a. Buat tiga skrip p1.sh, p2.sh, p3.sh**
echo -e '#!/bin/bash\necho "Ini proses p1"\nsleep 10\necho "p1 selesai"' > p1.sh
echo -e '#!/bin/bash\necho "Ini proses p2"\nsleep 10\necho "p2 selesai"' > p2.sh
echo -e '#!/bin/bash\necho "Ini proses p3"\nsleep 10\necho "p3 selesai"' > p3.sh
chmod +x p1.sh p2.sh p3.sh

**b. Jalankan skrip di background**
./p1.sh &
./p2.sh &
./p3.sh &
Melihat daftar proses:
jobs
ps aux | grep p[1-3].sh

5. Jobs
**a. Buat Shell Script pwaktu.sh yang Melakukan Loop**
Buat file pwaktu.sh:
echo -e '#!/bin/bash\nwhile true\ndo\ndate >> hasil\nsleep 10\ndone' > pwaktu.sh
chmod +x pwaktu.sh
Jalankan script:
./pwaktu.sh &
Script ini akan menyimpan tanggal dan waktu setiap 10 detik ke file hasil.

**b. Jalankan sebagai Background Process**
Jalankan perintah berikut untuk melihat daftar jobs:
jobs
Jalankan find sebagai background process:
find / -print > files 2>/dev/null &
jobs
**c. Pindahkan Job ke Foreground dan Kembalikan ke Background**
Gunakan fg untuk mengembalikan job ke foreground:
fg %1
Tekan Ctrl + Z untuk menghentikan sementara (suspend).
Gunakan bg untuk mengembalikan job ke background:
bg

**d. Stop Program Background Menggunakan kill**
Lihat proses yang berjalan:
ps x
Hentikan proses dengan kill:
kill [Nomor PID]

6. History
**a. Ubah Nilai HISTSIZE dari 1000 menjadi 20**
HISTSIZE=20
h
**b. Gunakan History untuk Mengulang Instruksi**
Jalankan kembali instruksi ke-5 dari history:
!5
Jalankan instruksi terakhir:
!!
Gunakan Ctrl + P dan Ctrl + N untuk navigasi history.

**c. Ulangi Instruksi pada Buffer Nomor 150**
!150
**d. Ulangi Instruksi dengan Prefiks ls**
!ls
