# Use Case Description - LAB (Pertemuan 3)

## LAB-UC03: Ajukan peminjaman
| Bagian | Isi |
| :--- | :--- |
| **Tujuan** | Menghasilkan pengajuan peminjaman yang tersimpan |
| **Aktor utama** | Mahasiswa |
| **Sumber kebutuhan** | LAB-R03 dan LAB-R04 |
| **Pemicu** | Mahasiswa memilih fungsi pengajuan peminjaman |
| **Prasyarat** | Mahasiswa telah terautentikasi; data peralatan tersedia |
| **Pascakondisi berhasil** | Pengajuan tersimpan dengan nomor dan status Menunggu keputusan |
| **Pascakondisi gagal** | Tidak ada pengajuan baru yang berhasil tersimpan |
| **Include** | LAB-UC04 — Periksa ketersediaan |
| **Extension point** | Bukti pengajuan tersedia, pada langkah 6 |
| **Extend** | LAB-UC05 jika [mahasiswa memilih cetak] |

**Alur Utama:**
1. Mahasiswa membuka pengajuan -> Sistem menampilkan formulir.
2. Mahasiswa memilih alat, jumlah, rentang waktu, dan tujuan -> Sistem menampung isian.
3. Mahasiswa mengirim pengajuan -> Sistem memeriksa kelengkapan data.
4. Sistem menjalankan LAB-UC04 (Periksa ketersediaan).
5. Jika tersedia, sistem menyimpan pengajuan dan memberikan nomor.
6. Mahasiswa melihat konfirmasi -> Sistem menampilkan nomor dan status (Mencapai *extension point*).
7. Mahasiswa mengakhiri pengajuan -> Sistem menutup proses pengajuan.

**Alur Alternatif / Pengecualian (Validasi Gagal):**
- Jika data tidak lengkap atau alat tidak tersedia pada langkah 4, sistem menampilkan pesan error. Pengajuan tidak disimpan (Pascakondisi gagal).
