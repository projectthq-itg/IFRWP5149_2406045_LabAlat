# Skenario Aktor LAB (Pertemuan 4)

| Aktor | Kedudukan | Tujuan terhadap sistem |
| :--- | :--- | :--- |
| **Peminjam** | Umum (General), baru P4 | Peran umum peminjam. Mewariskan fungsi ke Mahasiswa & Dosen. |
| **Mahasiswa** | Khusus dari Peminjam | Melihat ketersediaan, mengajukan peminjaman (warisan), + mencetak bukti. |
| **Dosen** | Khusus dari Peminjam | Melihat ketersediaan dan mengajukan peminjaman (warisan). |
| **Petugas Lab** | Tetap dari P3 | Mengelola alat, memproses keputusan, mencatat pengembalian. |
| **Kepala Lab** | Tetap dari P3 | Melihat laporan peminjaman. |

## Keputusan Pemodelan Generalization Aktor
- **Mahasiswa & Dosen** adalah bentuk khusus dari **Peminjam**.
- Asosiasi ke `LAB-UC01` (Lihat Ketersediaan) dan `LAB-UC03` (Ajukan Peminjaman) digambar **satu kali** dari aktor Peminjam.
- Asosiasi Mahasiswa ke `LAB-UC05` (Cetak Bukti) tetap digambar langsung dari Mahasiswa karena fungsi ini eksklusif milik Mahasiswa.