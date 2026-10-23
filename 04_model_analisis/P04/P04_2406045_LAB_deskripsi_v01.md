# Use Case Description Baru - LAB (Pertemuan 4)

## LAB-UC11: Catat Pengembalian Peralatan
| Elemen | Isi |
| :--- | :--- |
| **ID dan nama** | LAB-UC11: Catat Pengembalian Peralatan |
| **Sumber kebutuhan** | LAB-R09 dan LAB-R10 |
| **Tujuan** | Pengembalian tercatat dan status peminjaman serta kondisi peralatan terbarui |
| **Aktor utama** | Petugas Laboratorium |
| **Pemicu** | Petugas memilih fungsi pencatatan pengembalian dan menentukan peminjaman yang akan dikembalikan |
| **Prasyarat** | Petugas telah terautentikasi; peminjaman terpilih berstatus **Dipinjam** |
| **Pascakondisi berhasil** | Pengembalian tercatat dengan tanggal kembali dan kondisi peralatan; status peminjaman menjadi **Selesai** |
| **Pascakondisi gagal** | Tidak ada pengembalian baru yang tercatat; status peminjaman tidak berubah |
| **Include** | LAB-UC12: Periksa Kondisi Peralatan |
| **Collaboration** | LAB-CO02: Catat Pengembalian Peralatan |
| **Generalization** | Use case khusus (tidak termasuk hierarki LAB-UC02) |

**Alur Utama:**
1. Petugas memilih peminjaman yang akan dikembalikan -> Sistem menampilkan data peminjaman terpilih dan statusnya.
2. Petugas mengonfirmasi alat yang kembali dan jumlahnya -> Sistem menampung konfirmasi petugas.
3. Sistem memeriksa status peminjaman harus **Dipinjam**.
4. Sistem menjalankan **LAB-UC12**: memeriksa dan mencatat kondisi peralatan.
5. Petugas menyimpan pencatatan pengembalian -> Sistem menyimpan tanggal kembali dan kondisi; mengubah status peminjaman menjadi **Selesai**.
6. Petugas melihat konfirmasi -> Sistem menampilkan ringkasan pengembalian.

**Alur Alternatif / Pengecualian:**
- **A1 (Status bukan Dipinjam):** Pada langkah 3, sistem menolak pencatatan dan menampilkan status peminjaman saat ini. (Pascakondisi gagal berlaku).
- **A2 (Kondisi Rusak):** Pada langkah 4, jika kondisi *Rusak Ringan/Berat*, sistem tetap menyimpan pencatatan, menandai kondisi pada data peralatan. Pengembalian tetap tercatat (tidak otomatis denda).
- **A3 (Jumlah tidak sesuai):** Pada langkah 2, sistem meminta petugas memeriksa kembali isian sebelum penyimpanan.