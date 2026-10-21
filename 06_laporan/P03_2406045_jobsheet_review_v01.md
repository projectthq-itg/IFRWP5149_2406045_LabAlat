# Laporan Review & Konsistensi - Pertemuan 3

**Nama:** Muhammad Thoriq Mustaqim | **NIM:** 2406045

### 1. Uji Konsistensi Skenario
Sesuai instruksi, saya telah menguji tiga situasi pada model SIA dan LAB:

**a. Validasi berhasil dan pengguna tidak mengunduh/mencetak bukti**
- **Hasil:** Konsisten. Sistem menyimpan pengajuan (KRS/Peminjaman) dan mengubah status menjadi "Menunggu keputusan/persetujuan". Proses selesai tanpa error. Ini membuktikan relasi `«extend»` bersifat opsional.

**b. Validasi gagal**
- **Hasil:** Konsisten. Sistem menampilkan pesan error (misal: jadwal bentrok/alat tidak tersedia). Pengajuan tidak tersimpan (sesuai Pascakondisi Gagal). Ini membuktikan relasi `«include»` (Validasi/Periksa) berjalan wajib saat pengajuan.

**c. Validasi berhasil dan pengguna memilih mengunduh/mencetak bukti**
- **Hasil:** Konsisten. Sistem menyimpan pengajuan, lalu mencapai *extension point*. Karena pengguna memilih "Ya", sistem mengeksekusi use case tambahan (Cetak/Unduh bukti). Pengajuan tetap berhasil.

### 2. Catatan Perbaikan (Review)
- **Temuan:** Pada draf awal, garis asosiasi antara aktor Mahasiswa dan use case "Ajukan Peminjaman/KRS" sempat terputus karena salah menarik *anchor point*.
- **Perbaikan:** Memperbaiki garis agar menempel sempurna pada elemen. Memastikan panah putus-putus `«include»` mengarah dari Use Case Pengajuan ke Validasi, dan `«extend»` mengarah dari Cetak/Unduh ke Pengajuan. Tidak ada lagi panah generalisasi (segitiga).
