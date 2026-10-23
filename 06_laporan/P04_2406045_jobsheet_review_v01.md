# Laporan Review & Konsistensi - Pertemuan 4

**Nama:** Muhammad Thoriq Mustaqim | **NIM:** 2406045

### 1. Uji Konsistensi SIA
- **Situasi A (Mahasiswa melihat kalender tanpa asosiasi langsung):** Hal ini **benar** dan konsisten. Mahasiswa mewarisi fungsi dari aktor umum `Civitas Akademika`. Sesuai aturan generalization, asosiasi ke `SIA-UC07` digambar satu kali dari aktor umum.
- **Situasi B (Dosen bukan pengampu input nilai):** Sistem akan menolak aksi. Sesuai deskripsi `SIA-UC08`, prasyaratnya adalah dosen tersebut *harus* pengampu mata kuliah yang bersangkutan.
- **Situasi C (Admin hapus data mahasiswa yang masih aktif):** Sistem akan menolak aksi. Sesuai batasan tugas, Hapus Data Mahasiswa hanya untuk yang tidak memiliki data akademik aktif.

### 2. Catatan Perbaikan (Review)
- **Temuan:** Pada gambar awal, asosiasi `LAB-UC01` dan `LAB-UC03` masih ditarik dari Mahasiswa dan Dosen.
- **Perbaikan:** Asosiasi dihapus dari aktor khusus, lalu digambar satu garis dari aktor umum `Peminjam`. Lalu ditambahkan panah generalization (garis solid, ujung segitiga kosong) dari Mahasiswa dan Dosen menuju Peminjam. Asosiasi Mahasiswa ke `LAB-UC05` (Cetak Bukti) tetap dipertahankan karena eksklusif.