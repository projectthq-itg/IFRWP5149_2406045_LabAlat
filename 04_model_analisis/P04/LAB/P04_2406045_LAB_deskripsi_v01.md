# Use Case Description - LAB (Pertemuan 4)

## LAB-UC11: Catat Pengembalian Peralatan
| Elemen | Isi |
| :--- | :--- |
| **ID dan nama** | LAB-UC11: Catat Pengembalian Peralatan |
| **Sumber kebutuhan** | LAB-R09 dan LAB-R10 |
| **Tujuan** | Mencatat transaksi pengembalian alat dan memperbarui status peminjaman serta kondisi aset. |
| **Aktor utama** | Petugas Laboratorium |
| **Aktor pendukung** | - |
| **Pemicu** | Petugas memilih menu pengembalian dan memasukkan ID peminjaman. |
| **Prasyarat** | Petugas telah terautentikasi; status peminjaman saat ini adalah **Dipinjam**. |
| **Pascakondisi berhasil** | Data pengembalian (tanggal, kondisi alat) tersimpan; status peminjaman berubah menjadi **Selesai**. |
| **Pascakondisi gagal** | Tidak ada data pengembalian yang tersimpan; status peminjaman tidak berubah. |
| **Include** | LAB-UC12: Periksa Kondisi Peralatan |
| **Collaboration** | LAB-CO02: Catat Pengembalian Peralatan |

**Alur Utama:**
1. Petugas memasukkan ID peminjaman -> Sistem menampilkan detail alat dan status peminjaman.
2. Petugas mengonfirmasi jumlah alat yang kembali -> Sistem memvalidasi kecocokan jumlah.
3. Sistem memverifikasi status peminjaman harus **Dipinjam**.
4. Sistem menjalankan `LAB-UC12` (memeriksa kondisi fisik alat: Baik, Rusak Ringan, atau Rusak Berat).
5. Petugas menekan tombol "Simpan Pengembalian" -> Sistem menyimpan data dan mengubah status peminjaman menjadi **Selesai**.
6. Sistem menampilkan notifikasi sukses beserta ringkasan pengembalian.

**Alur Alternatif / Pengecualian:**
- **A1 (Status Tidak Sesuai):** Jika pada langkah 3 status peminjaman bukan "Dipinjam" (misal masih "Menunggu Keputusan"), sistem membatalkan proses dan menampilkan pesan *"Peminjaman belum dapat dikembalikan"*.
- **A2 (Kondisi Rusak):** Jika pada langkah 4 kondisi alat dicatat sebagai "Rusak Ringan/Berat", sistem tetap menyimpan data pengembalian, namun memberikan *flag* pada data peralatan untuk tindak lanjut. Denda tidak dihitung otomatis pada sistem ini.
- **A3 (Jumlah Tidak Sesuai):** Jika jumlah alat yang diinput tidak sama dengan jumlah yang dipinjam, sistem memunculkan *error validation* dan meminta petugas memeriksa kembali fisik alat.