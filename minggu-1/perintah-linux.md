1. pwd (print working directory)
   # Menampilkan lokasi direktori tempat kita berada saat ini.
   pwd

2. ls -la (list; -l = tampilan detail, -a = tampilkan file tersembunyi)
   # Menampilkan semua file dan folder secara detail.
   ls -la

3. cd (change directory)
   # Pindah ke direktori home pengguna.
   cd ~

4. mkdir -p (make directory; -p = buat folder induk bila belum ada)
   # Membuat folder minggu-1 dan subfolder latihan sekaligus.
   mkdir -p ~/minggu-1/latihan

5. touch
   # Membuat file kosong bernama catatan.txt.
   touch ~/minggu-1/latihan/catatan.txt

6. cp -r (copy; -r = salin folder beserta isinya)
   # Menyalin folder latihan menjadi backup-latihan.
   cp -r ~/minggu-1/latihan ~/minggu-1/backup-latihan

7. mv (move)
   # Mengganti nama catatan.txt menjadi catatan-baru.txt.
   mv ~/minggu-1/latihan/catatan.txt ~/minggu-1/latihan/catatan-baru.txt

8. rm (remove)
   # Menghapus file catatan-baru.txt (hanya file latihan).
   rm ~/minggu-1/latihan/catatan-baru.txt
   # Hati-hati: rm menghapus file tanpa memindahkannya ke Trash.

9. cat (concatenate)
   # Menampilkan isi file informasi sistem operasi.
   cat /etc/os-release

10. less
    # Membuka isi file untuk dibaca per halaman; tekan q untuk keluar.
    less /etc/os-release

11. head
    # Menampilkan 5 baris paling atas dari suatu file.
    head -n 5 /etc/os-release

12. tail
    # Menampilkan 5 baris paling bawah dari suatu file.
    tail -n 5 /etc/os-release

13. find
    # Mencari file catatan.txt di dalam folder minggu-1 dan seluruh subfoldernya.
    # File tersebut masih ada dalam folder backup-latihan.
    find ~/minggu-1 -name 'catatan.txt'

14. which
    # Menampilkan lokasi program/perintah ls.
    which ls

15. man (manual)
    # Membuka panduan penggunaan perintah ls; tekan q untuk keluar.
    man ls

Selesai.
