# Use Case Description Baru - SIA (Pertemuan 4)

## SIA-UC08: Input Nilai Mata Kuliah
| Elemen | Isi |
| :--- | :--- |
| **ID dan nama** | SIA-UC08: Input Nilai Mata Kuliah |
| **Sumber kebutuhan** | SIA-R08 |
| **Tujuan** | Nilai mata kuliah tersimpan di sistem |
| **Aktor utama** | Dosen |
| **Prasyarat** | Dosen telah terautentikasi dan merupakan pengampu mata kuliah tersebut. |
| **Pascakondisi berhasil** | Nilai tersimpan dan siap dipublikasikan. |
| **Pascakondisi gagal** | Nilai tidak tersimpan. |
| **Collaboration** | SIA-CO01: Input Nilai Mata Kuliah |

**Alur Utama:**
1. Dosen memilih mata kuliah yang diampu -> Sistem menampilkan daftar mahasiswa.
2. Dosen memasukkan nilai -> Sistem memvalidasi rentang nilai (misal 0-100).
3. Dosen menyimpan -> Sistem menyimpan nilai.

**Alur Alternatif:**
- **Validasi Gagal:** Jika nilai di luar rentang, sistem menolak penyimpanan dan menampilkan pesan error.

## SIA-UC09: Lihat KHS
| Elemen | Isi |
| :--- | :--- |
| **ID dan nama** | SIA-UC09: Lihat KHS |
| **Aktor utama** | Mahasiswa |
| **Prasyarat** | Nilai semester tersebut sudah dipublikasikan. |
| **Collaboration** | SIA-CO02: Lihat KHS |

**Alur Utama:**
1. Mahasiswa memilih semester -> Sistem menampilkan KHS (hanya nilai yang sudah dipublikasikan).