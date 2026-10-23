# Skenario Aktor SIA (Pertemuan 4)

| Aktor | Kedudukan | Tujuan terhadap sistem |
| :--- | :--- | :--- |
| **Civitas Akademika** | Umum (General), baru P4 | Peran umum. Mewariskan fungsi ke Mahasiswa & Dosen. |
| **Mahasiswa** | Khusus dari Civitas | Melihat kalender (warisan), melihat KHS, mengajukan KRS. |
| **Dosen** | Khusus dari Civitas | Melihat kalender (warisan), input nilai, menjadi dosen wali. |
| **Admin Akademik** | Tetap dari P2 & P3 | Mengelola jadwal kuliah & data mahasiswa. |

## Keputusan Pemodelan
- **Mahasiswa & Dosen** adalah bentuk khusus dari **Civitas Akademika**.
- Asosiasi ke `SIA-UC07` (Lihat Kalender Akademik) digambar satu kali dari Civitas Akademika.