# Use Case Description - SIA (Pertemuan 4)

## SIA-UC08: Input Nilai Mata Kuliah
| Elemen | Isi |
| :--- | :--- |
| **ID dan nama** | SIA-UC08: Input Nilai Mata Kuliah |
| **Sumber kebutuhan** | SIA-R08 |
| **Tujuan** | Memasukkan dan menyimpan nilai mahasiswa untuk mata kuliah yang diampu. |
| **Aktor utama** | Dosen |
| **Pemicu** | Dosen membuka menu input nilai dan memilih kelas/mata kuliah. |
| **Prasyarat** | Dosen telah terautentikasi dan **terdaftar sebagai pengampu** mata kuliah tersebut. |
| **Pascakondisi berhasil** | Nilai tersimpan di *database* dan siap untuk dipublikasikan. |
| **Pascakondisi gagal** | Nilai tidak tersimpan. |
| **Collaboration** | SIA-CO01: Input Nilai Mata Kuliah |

**Alur Utama:**
1. Dosen memilih mata kuliah -> Sistem menampilkan daftar mahasiswa KRS.
2. Dosen menginput nilai (angka/huruf) per mahasiswa -> Sistem menampung *input*.
3. Dosen menekan tombol "Simpan" -> Sistem memvalidasi rentang nilai.
4. Sistem menyimpan nilai dan menampilkan pesan sukses.

**Alur Alternatif / Pengecualian:**
- **A1 (Validasi Gagal):** Jika nilai yang diinput di luar rentang yang sah (misal > 100 atau < 0), sistem menolak penyimpanan dan menyorot kolom yang salah.
- **A2 (Bukan Pengampu):** Jika dosen yang login mencoba mengakses ID mata kuliah yang bukan ampuannya, sistem memblokir akses halaman.

## SIA-UC09: Lihat KHS (Ringkas)
- **Aktor Utama:** Mahasiswa.
- **Prasyarat:** Nilai semester tersebut telah dipublikasikan secara resmi.
- **Alur:** Mahasiswa memilih semester -> Sistem *query* nilai yang berstatus *published* -> Sistem menampilkan Kartu Hasil Studi (KHS).
- **Pengecualian:** Jika nilai belum dipublikasikan, sistem menampilkan pesan *"Nilai semester ini belum tersedia"*.