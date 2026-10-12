# Voucher Entri Kas Keluar

## Identitas Tugas

| Keterangan | Detail |
|---|---|
| Nama | Hanindya Sabrinawati |
| NIM | 12030124130112 |
| Mata Kuliah | Pengkodean dan Pemrograman |
| Kelas | G |
| Dosen Pengampu | Dr. Totok Dewayanto, S.E., M.Si., Akt. |

*Disusun untuk memenuhi Tugas Project UTS Pengkodean dan Pemrograman.*

## Deskripsi

Aplikasi web sederhana untuk membuat Bukti Kas Keluar (BKK) dan memasukkan rincian jurnal debit/kredit. Antarmuka menggunakan Bahasa Indonesia dan menampilkan nilai transaksi dalam Rupiah (IDR).

## Fitur

- Mengisi nomor voucher, tanggal transaksi, penanggung jawab, penerima pembayaran, dan deskripsi.
- Menambah dan menghapus baris jurnal.
- Memasukkan akun beserta nilai debit dan kredit.
- Menghitung total debit/kredit secara otomatis dan memeriksa keseimbangan jurnal.
- Menyimpan voucher beserta rincian jurnal ke Supabase PostgreSQL melalui backend.
- Menampilkan notifikasi apabila penyimpanan berhasil atau gagal.

## Struktur Folder

| Folder/Berkas | Keterangan |
|---|---|
| `Frontend/` | Halaman aplikasi (`index.html`), logika formulir, dan stylesheet. |
| `Backend/app.js` | Server lokal dan endpoint untuk menyimpan voucher ke Supabase. |
| `Backend/schema.sql` | Skema tabel PostgreSQL dan fungsi penyimpanan transaksi voucher. |
| `Backend/start.bat` | Menjalankan server backend di Windows. |

## Persiapan Supabase

1. Buka Supabase Dashboard proyek, pilih **SQL Editor**, lalu jalankan seluruh isi `Backend/schema.sql`.
2. Siapkan URL proyek dan **service role key** dari pengaturan API proyek Supabase. Backend menggunakan key ini untuk memanggil fungsi PostgreSQL melalui Supabase API. Jangan menaruh key di frontend, membagikannya, atau mengunggahnya ke repositori publik.

## Menjalankan Aplikasi

Gunakan Node.js versi 18 atau lebih baru. Di PowerShell, atur variabel berikut dengan kredensial proyek Supabase:

```powershell
$env:SUPABASE_URL = "https://project-ref.supabase.co"
$env:SUPABASE_SERVICE_ROLE_KEY = "service-role-key"
Set-Location "Backend"
.\start.bat
```

Setelah server berjalan, buka [http://localhost:3000](http://localhost:3000). Isi nama penanggung jawab dan penerima pembayaran, pastikan jurnal seimbang, lalu pilih **Submit Voucher**.
