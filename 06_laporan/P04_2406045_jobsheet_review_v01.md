# Laporan Review & Konsistensi - Pertemuan 4

**Nama:** Muhammad Thoriq Mustaqim | **NIM:** 2406045

### 1. Uji Konsistensi Skenario SIA (Berdasarkan Instruksi Halaman 22)

**Situasi A: Mahasiswa melihat kalender akademik tanpa garis asosiasi langsung.**
*   **Analisis:** Hal ini **diperbolehkan dan benar** secara notasi UML. Mahasiswa merupakan aktor khusus yang mewarisi (inherit) perilaku dari aktor umum `Civitas Akademika`. Oleh karena itu, garis asosiasi digambar satu kali dari Civitas Akademika ke `SIA-UC07 Lihat Kalender Akademik`. Mahasiswa tetap bisa mengaksesnya karena hubungan pewarisan (garis solid dengan segitiga kosong menunjuk ke Civitas Akademika).

**Situasi B: Dosen yang bukan pengampu mencoba menginput nilai.**
*   **Analisis:** Sistem harus **menolak aksi** tersebut. Berdasarkan Use Case Description `SIA-UC08 Input Nilai Mata Kuliah`, prasyarat mutlaknya adalah dosen tersebut harus terautentikasi **dan** merupakan pengampu dari mata kuliah yang dipilih. Jika bukan pengampu, sistem tidak akan menampilkan form input atau akan memberikan pesan error akses ditolak.

**Situasi C: Admin Akademik menghapus data mahasiswa yang masih memiliki data akademik aktif.**
*   **Analisis:** Sistem harus **menolak aksi** penghapusan. Sesuai batasan tugas pada Jobsheet halaman 20, aturan `SIA-UC13 Hapus Data Mahasiswa` menyatakan bahwa penghapusan hanya boleh dilakukan jika mahasiswa tersebut *tidak memiliki data akademik aktif*. Jika dipaksa hapus, sistem akan memunculkan peringatan pelanggaran aturan bisnis (business rule).

### 2. Catatan Perbaikan Notasi (Review v01 ke v02)
*   **Temuan 1:** Pada draf awal diagram LAB, garis asosiasi dari `Mahasiswa` ke `Ajukan Peminjaman` dan `Lihat Ketersediaan` masih digambar ganda (dari Mahasiswa dan Dosen).
*   **Perbaikan 1:** Menghapus garis tersebut dari aktor khusus, dan menggambar satu garis dari aktor umum `Peminjam`. Ditambahkan panah *generalization* (segitiga kosong) dari Mahasiswa dan Dosen menuju Peminjam. Asosiasi khusus Mahasiswa ke `Cetak Bukti` tetap dipertahankan.
*   **Temuan 2:** Relasi *Realization* (garis putus-putus segitiga kosong) sempat digambar terbalik.
*   **Perbaikan 2:** Memperbaiki arah panah agar selalu berasal dari `Collaboration` (elips putus-putus) menuju `Use Case` yang direalisasikannya.