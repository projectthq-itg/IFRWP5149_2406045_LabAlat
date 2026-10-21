# Use Case Description - SIA KRS (Pertemuan 3)

## SIA-UC03: Ajukan KRS
| Bagian | Isi |
| :--- | :--- |
| **Tujuan** | Menghasilkan pengajuan KRS yang tersimpan |
| **Aktor utama** | Mahasiswa |
| **Sumber kebutuhan** | SIA-R03, SIA-R04, SIA-R05 |
| **Pemicu** | Mahasiswa memilih menu pengajuan KRS |
| **Prasyarat** | Mahasiswa terautentikasi, data mata kuliah & jadwal tersedia |
| **Pascakondisi berhasil** | KRS tersimpan dengan status Menunggu persetujuan dosen wali |
| **Pascakondisi gagal** | KRS tidak tersimpan |
| **Include** | SIA-UC04 — Validasi KRS |
| **Extension point** | Konfirmasi penyimpanan, pada langkah 6 |
| **Extend** | SIA-UC05 jika [mahasiswa memilih unduh bukti] |

**Alur Utama:**
1. Mahasiswa membuka form KRS -> Sistem menampilkan daftar mata kuliah.
2. Mahasiswa memilih mata kuliah -> Sistem menampung pilihan.
3. Mahasiswa submit pengajuan -> Sistem menjalankan SIA-UC04 (Validasi KRS).
4. Jika validasi lolos, sistem menyimpan KRS berstatus Menunggu persetujuan dosen wali.
5. Sistem menampilkan nomor pengajuan dan status.
6. Mahasiswa melihat konfirmasi (Mencapai *extension point*).

**Alur Alternatif (Validasi Gagal):**
- Pada langkah 3, jika validasi gagal (kelengkapan kurang, prasyarat tidak terpenuhi, benturan jadwal), sistem menampilkan pesan kesalahan spesifik dan KRS belum berhasil tersimpan.

## SIA-UC05: Proses keputusan KRS
| Bagian | Isi |
| :--- | :--- |
| **Tujuan** | Menetapkan status persetujuan KRS |
| **Aktor utama** | Dosen Wali |
| **Sumber kebutuhan** | SIA-R06 |
| **Pemicu** | Dosen membuka daftar pengajuan KRS mahasiswa |
| **Prasyarat** | Terdapat KRS berstatus Menunggu persetujuan |
| **Pascakondisi berhasil** | Status KRS berubah menjadi Disetujui atau Ditolak beserta catatan |

**Alur Utama:**
1. Dosen membuka daftar KRS -> Sistem menampilkan antrean pengajuan.
2. Dosen memilih KRS mahasiswa -> Sistem menampilkan detail.
3. Dosen memilih "Setujui" atau "Tolak" dan mengisi catatan -> Sistem memperbarui status KRS dan menyimpan catatan.
