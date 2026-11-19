# Minggu 1 - Latihan Perintah Linux

Materi: Command Line dan The Filesystem  
Referensi: https://linuxjourney.com/

## 1. Persiapan latihan

Jalankan perintah berikut di Terminal Ubuntu supaya semua latihan berada di folder pribadi, bukan di folder penting sistem.

```bash
mkdir -p ~/minggu-1/latihan-linux/dokumen
cd ~/minggu-1/latihan-linux
touch kosong.txt hapus-saya.txt
printf 'Baris pertama\nBaris kedua\nBaris ketiga\nBaris keempat\n' > catatan.txt
```

Keterangan:
- `~` berarti direktori home pengguna yang sedang login.
- `latihan-linux` adalah folder latihan, jadi tidak mengganggu berkas sistem.
- `catatan.txt` berisi empat baris untuk latihan membaca file.
- Perintah `printf ... > catatan.txt` mengisi atau menimpa file bernama `catatan.txt`. Gunakan hanya pada file latihan.

## 2. Contoh 15 perintah Linux

### 1. `pwd`

Fungsi: Melihat lokasi direktori tempat kita berada sekarang.

```bash
pwd
```

Analogi: Mengecek posisi kita di peta.

### 2. `ls -la`

Fungsi: Melihat daftar seluruh file dan folder, termasuk yang tersembunyi, dengan informasi detail.

```bash
ls -la
```

Keterangan: `-l` menampilkan detail; `-a` menampilkan semua termasuk file tersembunyi.

Analogi: Melihat daftar lengkap barang dalam sebuah ruangan.

### 3. `cd`

Fungsi: Berpindah direktori.

```bash
cd ~/minggu-1/latihan-linux
```

Contoh tambahan: `cd ..` berpindah ke direktori induk; `cd ~` kembali ke home.

Analogi: Berjalan dari satu ruangan ke ruangan lain.

### 4. `mkdir -p`

Fungsi: Membuat direktori dan direktori induk yang belum ada.

```bash
mkdir -p dokumen/arsip
```

Analogi: Membuat lemari baru sekaligus laci di dalamnya.

### 5. `cp -r`

Fungsi: Menyalin sebuah folder beserta seluruh isinya.

```bash
cp -r dokumen dokumen-salinan
```

Analogi: Memfotokopi satu map beserta semua dokumen di dalamnya.

### 6. `mv`

Fungsi: Memindahkan atau mengganti nama file/folder.

```bash
mv kosong.txt dokumen/arsip/kosong.txt
```

Analogi: Memindahkan dokumen dari meja ke laci.

### 7. `rm`

Fungsi: Menghapus file. Gunakan `-i` supaya diminta konfirmasi.

```bash
rm -i hapus-saya.txt
```

Ketika ditanya, ketik `y` untuk menghapus atau `n` untuk membatalkan.

Analogi: Membuang dokumen, tetapi memastikan terlebih dahulu bahwa dokumennya benar.

**Peringatan:** Jangan mencoba `rm -rf` pada folder atau data penting. Opsi `-r` berarti menghapus isi folder secara rekursif; `-f` berarti memaksa tanpa konfirmasi biasa.

### 8. `touch`

Fungsi: Membuat file kosong, atau memperbarui waktu modifikasi file yang sudah ada.

```bash
touch baru.txt
```

Analogi: Menyiapkan selembar kertas kosong.

### 9. `cat`

Fungsi: Menampilkan isi file teks langsung di Terminal.

```bash
cat catatan.txt
```

Analogi: Membaca satu lembar dokumen dari awal sampai akhir.

### 10. `less`

Fungsi: Membaca isi file secara bertahap, cocok untuk file panjang.

```bash
less catatan.txt
```

Tekan `q` untuk keluar.

Analogi: Membaca buku sambil membalik halaman.

### 11. `head`

Fungsi: Menampilkan baris-baris paling awal dari file. Secara default 10 baris.

```bash
head -n 2 catatan.txt
```

Analogi: Membaca dua baris pertama sebuah dokumen.

### 12. `tail`

Fungsi: Menampilkan baris-baris paling akhir dari file. Secara default 10 baris.

```bash
tail -n 2 catatan.txt
```

Analogi: Membaca dua baris terakhir sebuah dokumen.

### 13. `find`

Fungsi: Mencari file atau folder berdasarkan lokasi dan kriteria tertentu.

```bash
find . -name '*.txt'
```

Keterangan: `.` berarti direktori saat ini; `*.txt` berarti semua nama berakhiran `.txt`.

Analogi: Mencari seluruh dokumen berjenis tertentu di lemari dan laci.

### 14. `which`

Fungsi: Menunjukkan lokasi program yang ditemukan lewat PATH.

```bash
which ls
```

Analogi: Bertanya di mana peralatan tertentu disimpan.

### 15. `man`

Fungsi: Membuka buku panduan penggunaan suatu perintah.

```bash
man ls
```

Tekan `q` untuk keluar. Jika muncul `man: command not found`, paket dokumentasi `man-db` mungkin belum terpasang.

Analogi: Membuka buku petunjuk penggunaan peralatan.

## 3. Ringkasan materi filesystem

| Direktori | Fungsi umum | Analogi |
| --- | --- | --- |
| `/etc` | Konfigurasi sistem dan layanan | Ruang pengaturan gedung |
| `/var` | Data berubah seperti log/cache | Buku catatan aktivitas |
| `/home` | Data pribadi pengguna | Loker setiap orang |
| `/usr` | Program, library, dan data aplikasi | Gudang peralatan kerja |
| `/tmp` | File sementara | Meja kerja sementara |

### Path absolut dan relatif

Path absolut dimulai dari `/` dan menunjukkan alamat lengkap. Contoh: `/home/andi/dokumen/catatan.txt`.

Path relatif bergantung pada direktori tempat kita berada. Jika sudah berada di `/home/andi`, contoh relatifnya adalah `dokumen/catatan.txt`.

Analogi: Path absolut seperti alamat lengkap rumah. Path relatif seperti petunjuk 'belok kanan' dari posisi sekarang.

### Kenapa `rm -rf` berbahaya?

`rm -rf` dapat menghapus folder beserta semua isinya tanpa konfirmasi biasa. Salah lokasi atau salah nama dapat menghapus data penting. Penghapusan ini biasanya tidak masuk Trash.

Kebiasaan aman:
1. Jalankan `pwd` untuk memeriksa lokasi sekarang.
2. Jalankan `ls -la nama-folder` untuk memeriksa target.
3. Utamakan `rm -i nama-file` saat belajar.
4. Hindari `sudo` dan `rm -rf` jika tidak benar-benar perlu.
5. Buat backup data penting.

## 4. Hasil latihan yang diharapkan

Sesudah mencoba perintah-perintah di atas, kamu seharusnya bisa:
- Mengetahui posisi direktori sekarang.
- Melihat, membuat, menyalin, memindahkan, mencari, dan menghapus file latihan.
- Membaca isi file menggunakan `cat`, `less`, `head`, dan `tail`.
- Mencari lokasi program dan membuka manual perintah.
- Menjelaskan folder penting Linux serta bahaya penghapusan rekursif.
